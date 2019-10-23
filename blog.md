---
layout: page
title: Blog
active: blog
published: true
---

<div>
<ul>
  	{% for post in site.posts %}
      <li><span>{{ post.date | date: "%Y-%m-%d" }} &raquo; </span><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
</div>

<div>
  {% comment %}Posts will be filtered by one category{% endcomment %}
  {% assign filterCategory = "works" %}

  {% for tag in site.tags %}
      {% comment %}creates an empty array{% endcomment %}
      {% assign postsInCategory = "" | split: "/" %}

      {% comment %}looping over site.tags{% endcomment %}
      {% for post in tag[1] %}
          {% if post.categories contains filterCategory %}
              {% comment %}if a post is from our filter category we add it to postsInCategory array{% endcomment %}
              {% assign postsInCategory = postsInCategory | push: post %}
          {% endif %}
      {% endfor %}

      {% if postsInCategory.size > 0 %}
          <h1>{{ tag[0] }}</h2>
          {% for post in postsInCategory %}
              <h2><a href="{{ site.baseurl }}{{ post.url }}"></a>{{ post.title }}</h2>
          {% endfor %}
      {% endif %}
  {% endfor %}
</div>
