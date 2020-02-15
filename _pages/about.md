---
permalink: /
title: "Learning Out Loud"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I'm a member of the [OpenAI Scholars Program 2020 Cohort](https://openai.com/blog/openai-scholars-spring-2020/) and this is my blog about artificial intelligence and deep learning. 

Posts
=========
{% include base_path %}
{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% include archive-single.html %}
{% endfor %}
