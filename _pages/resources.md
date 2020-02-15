---
permalink: /resources/
title: "Resources"
author_profile: true
---

## Deep learning/AI Courses

There are two very popular and well respected "intro to AI" type courses that I can recommend. Both are aimed at lay people and taught by excellent educators. Many people have worked their way through one or both of these courses to get into the field. 

1. [Fast.ai](https://fast.ai/) - This course is split into two parts. Each lasts about 6 months if you work through them in thorough detail. (You can watch the videos for both parts of the course for free.) Part 1 takes a very practical approach to help you get up to speed doing machine learning work for your field as quickly as possible. It covers some theory, but is more concerned with application first. Part 2 is more theoretical and works through the process of building the code from Part 1. If you want to know how to do the practice of deep learning to process data, but aren't as concerned with being a deep learning researcher or developing new algorithms, then Part 1 (classes 1-7) of this course is for you. 

2. [Deeplearning.io](https://deeplearning.io/) - This is a series of five courses available on Coursera, and all together they are intended to take four to six months at 10 to 15 hours per week. As of Spring 2020, this costs $50 / month (independent of how long you spend on the courses) for people in the US. Andrew Ng from Stanford teaches all of these courses and he slowly builds up the theory of deep learning from scratch. This course assumes knowledge of linear algebra (vectors and matrices) and basic programming (in Python). If you have taken calculus, that will make some of the formulas more obvious, but calculus is not required for the course. If you want to become a deep learning researcher, definitely consider starting with this course.  

## Deep learning/AI Computers 

In order to do most machine learning today, you need access to a computer with a high end Nvidia Graphics card. Sadly, AMD graphics cards won't work today without great effort. For a lot more detail on this, see [this excellent post](https://timdettmers.com/2019/04/03/which-gpu-for-deep-learning/), which gets updated every couple of years to keep pace with new tech. The most important quote (as of early 2020) is:

> ## **TL;DR advice**
>
>**Best GPU overall:** RTX 2070
>
>**GPUs to avoid:** Any Tesla card; any Quadro card; any Founders Edition card; Titan RTX, Titan V, Titan XP
>
>**Cost-efficient but expensive:** RTX 2070
>
>**Cost-efficient and cheap:**  RTX 2060, GTX 1060 (6GB).
>
>**I have little money:** GTX 1060 (6GB)
>
>**I have almost no money:** GTX 1050 Ti (4GB).Alternatively: CPU (prototyping) + AWS/TPU >(training); or Colab.
>
>**I do Kaggle:** RTX 2070. If you do not have enough money go for a GTX 1060 (6GB) or GTX Titan (Pascal) from eBay for prototyping and AWS for final training. Use fastai library.
>
>**I am a competitive computer vision or machine translation researcher:** GTX 2080 Ti with the blower fan design. If you train very large networks get RTX Titans.
>
>**I am an NLP researcher:** RTX 2080 Ti use 16-bit.


There are two main ways to get access to a computer with this kind of GPU. The first is to rent it from one of the many online/cloud providers. The second is to buy or build one yourself. The cloud approach is much faster and easier, and in the short term it's also cheaper. If you're just breaking into the field, not sure how long you want to be involved, and need something quickly, this is definitely way to go. The easiest, most competitively priced cloud AI service changes frequently, so I would check out [Fast.ai](https://fast.ai/) for recommendations on the best place for you *now*.

If you're very confident you want to be in machine learning for a while, have time to spend configuring Linux, and don't mind spending a few thousand dollars right now in order to save money over the long term, then you should buy or build your own server. Here are a coule of good vendors for pre-built, pre-configured Linux AI machines:

* [System76](https://system76.com/) - They sell high quality Linux machines with options to add the kinds of hig end GPUs you need for deep learning. This is a good source for a person wanting to break into the field.
* [Lambda Labs](https://lambdalabs.com/) - They sell *high end* deep learning workstations, preconfigured with multiple GPUs and deep learning software. This is a good source for a business trying to develop a small AI team. 

If you want something a little cheaper and have a desktop around that you're willing to run Linux on and install a GPU in, then you should go for [Ubuntu Linux](https://ubuntu.com/download) which is the most popular Linux used in AI today, or [Pop!_OS](https://system76.com/pop), which is a compatible derivative of Ubuntu that has a lot of nice stuff built in to make it nicer to use. As for where to buy a GPU, Ebay or Amazon are both good choices. 

## Deep learning/AI Technologies to learn

### Python
Most AI work today is done in [Python](https://www.python.org/). If you don't know how to program yet, python is a great language to learn in. If you know how to program but don't know Python yet, you can learn it quickly. The first step in learning about AI today is learning a little Python. You don't need a ton, just enough to write a basic program. 

### Jupyter 
[Jupyter Notebook](https://jupyter.org/) is a very simple way to create documents with live python code in them. This tool is used by most people in AI/DL/ML today. 

### PyTorch
PyTorch is an easy to use library for building and training deep learning models. OpenAI recently [announced](https://openai.com/blog/openai-pytorch/) that they are consolidating thier work on PyTorch

* [This video](https://www.youtube.com/watch?v=_H3aw6wkCv0) is an excellent introduction to PyTorch
*  Alternately, you can clone and work through [this repo](https://github.com/sotte/pytorch_tutorial). If you do, then start with the [foreword.ipynb](https://github.com/sotte/pytorch_tutorial/blob/master/notebooks/foreword.ipynb) notebook. 

