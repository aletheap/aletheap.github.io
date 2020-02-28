---
permalink: /pytorch-tips/
title: "PyTorch Tips"
author_profile: true
---

## General shape of a pytorch program

Supervised learning pytorch programs have a general basic shape that is approximately the same between them all. It looks like this:

Import stuff

```
import os

import matplotlib.pyplot as plt
import numpy as np

import torch
from torch import nn
from torch.utils.data import DataLoader

import torchvision
from torchvision import transforms
```

Pick a device to run your stuff on:
```
use_cuda = torch.cuda.is_available()
cuda_dev = "cuda:0"
device = torch.device(cuda_dev if use_cuda else "cpu")
print(device)
if use_cuda:
    print('-', torch.cuda.get_device_name(cuda_dev_num))
```

Load (and maybe trandform) your data:
```
datadir = "/home/apower/data/oxford-iiit-pet"
traindir = os.path.join(datadir, 'train')
devdir = os.path.join(datadir, 'dev')
testdir = os.path.join(datadir, 'test')

X_train = torchvision.datasets.ImageFolder(traindir, transform)
X_dev = torchvision.datasets.ImageFolder(devdir, transform)
X_test = torchvision.datasets.ImageFolder(testdir, transform)

num_labels = len(X_train.classes)

print('training_set:', len(X_train), '\ndev_set:', len(X_dev), '\ntest_set:', len(X_test), '\nlabels:', num_labels)

train_loader = DataLoader(X_train, batch_size=256, shuffle=True, num_workers=4)
dev_loader = DataLoader(X_dev, batch_size=1)
test_loader = DataLoader(X_test, batch_size=1)
```

Define your model:
```
model = nn.Resnet34()
if use_cuda:
    model = model.to(device)
```

Define optimizer and loss measure:
```
criterion = nn.CrossEntropyLoss()
optimizer = torch.optim.SGD(model.parameters(), lr=0.1)
```

Loop over the training data to learn:
```
losses = [10**10]
max_epochs = 20
for epoch in range(max_epochs):
    batch = 0
    for local_batch, local_labels in train_loader:
        # Transfer to GPU
        X, y = local_batch.to(device), local_labels.to(device)
        y_pred = model.forward(X)
        loss = criterion(y_pred, y)
        losses.append(loss.item())
        optimizer.zero_grad()
        loss.backward()
        optimizer.step()
        #print('epoch:', epoch, 'batch:', batch, 'loss:', loss.item())
        batch += 1
    print('epoch:', epoch, 'loss:', loss.item())
```

This pattern (import, cuda_device, load_data, model, optimizer, criterion, epoch loop) is the general shape of pytorch supervised learnign programs.

## Frameworks on top of PyTorch:

[This post](https://towardsdatascience.com/pytorch-lightning-vs-pytorch-ignite-vs-fast-ai-61dc7480ad8a) has a great comparison of [fast.ai](https://github.com/fastai/fastai2), [pytorch-lightning](https://github.com/PyTorchLightning/pytorch-lightning), and [ignite](https://github.com/pytorch/ignite). The short summary is this: 

* [fastai](https://github.com/fastai/fastai2) - If you're new to deep learning and really just want to get something functional without having to understand all the subtleties of the most cutting edge tweaks, go with this. 
* [pytorch-lightning](https://github.com/PyTorchLightning/pytorch-lightning) - If you want to implement supervised learning yourself and have the library automatically handle tensorboard and scaling across GPUs and nodes and such, go with this. 
* [ignite](https://github.com/pytorch/ignite) - If you want more flexiblity and control and/or need to do reinforcement learning, go with this.