---
title: "Douglas Day's Blog"
---

I will post the content that I'm learning here.

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
