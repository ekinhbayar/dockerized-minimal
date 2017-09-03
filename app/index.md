---
layout: default
description: Site Description
---

<h2>Recent Posts</h2>
{% for post in site.posts limit:50 %}
<h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
<div class="preview">
    {% if post.description %}
    <span class="body">{{ post.description | strip_html | truncatewords: 300 }}</span>
    {% else %}
    <span class="body">{{ post.excerpt | strip_html }}</span>
    {% endif %}
</div>
{% endfor %}
