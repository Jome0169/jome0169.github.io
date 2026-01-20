---
layout: page
title: Old Postings
nav_title: Old Postings
weight: 20
---

## Old Postings

<ul>
  {% for post in site.categories['Old Postings'] %}
    <li>
      <h3><a href="{{ post.url | absolute_url }}">{{ post.title }}</a></h3>
      <p>{{ post.excerpt }}</p>
      <p><a href="{{ post.url | absolute_url }}">Read more...</a></p>
    </li>
  {% endfor %}
</ul>