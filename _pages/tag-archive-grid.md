---
title: "Posts by Tag (grid view)"
permalink: /tags-grid/
layout: single
entries_layout: grid
author_profile: true
---

{% assign tags =  site.note | map: 'tags' | join: ','  | split: ',' | uniq %}
{% for tag in tags %}
  <h3>{{ tag }}</h3>
  <ul>
  {% for note in site.note %}
    {% if note.tags contains tag %}
    <li><a href="{{ site.baseurl }}{{ note.url }}">{{ note.title }}</a></li>
    {% endif %}
  {% endfor %}
  </ul>
{% endfor %}