---
# Featured tags need to have the `list` layout.
layout: list

# The title of the tag's page.
title: Archive

# (Optional) Write a short (~150 characters) description of this featured tag.
description: >
  This is a featured category, which have their own page.

# Setting `menu` will generate an entry in the sidebar for this tag.
menu: true
order: 10
---

<h1>Archive of posts with {{ page.type }} '{{ page.title }}'</h1>
<ul class="posts">
  {% for post in page.posts %}
    <li>
      <span class="post-date">{{ post.date | date: "%b %-d, %Y" }}</span>
      <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>


<h1>Archive of posts from {{ page.date | date: "%B %Y" }}</h1>

<ul class="posts">
{% for post in page.posts %}
  <li>
    <span class="post-date">{{ post.date | date: "%b %-d, %Y" }}</span>
    <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>
