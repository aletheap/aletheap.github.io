---
permalink: /
title: "Learning Out Loud"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Welcome! I'm a member of the [OpenAI Scholars Program 2020 Cohort](https://openai.com/blog/openai-scholars-spring-2020/) and this is where I'm planning to blog about my experiences of learning about artificial intelligence. 


{% include base_path %}
{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% include archive-single.html %}
{% endfor %}
