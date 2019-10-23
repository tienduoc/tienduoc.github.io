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
{% for category in page.categories %}
  {% assign moreThanOneInCategory = false %}
  {% assign posts = site.categories[category] %}

  {% for post in posts %}
    {% if forloop.length > 1 %}
      {% assign moreThanOneInCategory = true %}
    {% endif %}
  {% endfor %}

  {% if moreThanOneInCategory == true %}
    <div class="related-posts">
      <h3>Other posts archived in “{{ category }}”</h3>

      <ul>
        {% for post in posts %}
          {% unless post.url == page.url %}
            <li>
              <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>

              Published on <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time>
            </li>
          {% endunless %}
        {% endfor %}
      </ul>
    </div>
  {% endif %}
{% endfor %}
</div>
