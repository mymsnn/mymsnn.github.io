---
layout: page
title: Blog Archive
---

{% for tag in site.tags %}
  <h3 id="{{ tag[0] | slugify }}">{{ tag[0] }}</h3>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ post.url | relative_url }}">{{ post.date | date: "%B %Y" }} - {{ post.title | escape }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
