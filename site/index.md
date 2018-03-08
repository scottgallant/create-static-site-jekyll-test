---
layout: default
title: Homepage
---
Hello world! I'm `site/index.md`

## Posts

{% for post in site.posts %}
  <a href="{{ post.url | absolute_url }}" title="View {{ post.title }}">{{ post.title }}</a>
{% endfor %}


{% for project in site.projects %}
  {% capture now_unix %}{{'now' | date: '%s'}}{% endcapture %}
  {% capture project_time %}{{project.date | date: '%s'}}{% endcapture %}
  {% if project_time < now_unix %}
   <h1>{{ project.title }}</h1>
   {{ project.content }}
  {% endif %}
{% endfor %}
