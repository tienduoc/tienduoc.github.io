---
layout: page
title: Blog
active: blog
---

<div>
<ul>
    {% post.title contains "Angular" %}
    <h3>Angular</h3>
      <li><span>{{ post.date | date: "%Y-%m-%d" }} &raquo; </span><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
</div>


