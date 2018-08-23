---
layout: archive
permalink: /ai/
title: "Data Science & ML"
author_profile: true
---

{% include base_path %}
{% include group-by-array collection=site.posts field="category" %}

{% for category in group_names %}
  {% assign posts = group_items[forloop.index0] %}  
  {% for post in posts %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}    