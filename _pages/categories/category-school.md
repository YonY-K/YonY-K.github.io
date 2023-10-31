---
title: "학원공부"
layout: archive
permalink: categories/school
author_profile: true
types: posts
---

{% assign posts = site.categories['school']%}
{% for post in posts %}
  {% include archive-single.html type=page.entries_layout %}
{% endfor %}
