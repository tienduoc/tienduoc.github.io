---
layout: page
title: Blog
active: blog
---

<div>
<ul>
    {% post.title contains "Angular" %}
    ####Angular
      <li><span>{{ post.date | date: "%Y-%m-%d" }} &raquo; </span><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
</div>


