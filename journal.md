---
layout: page
title: Journal
permalink: /journal/
---

What we build and why, including what did not work.

{% assign entries = site.categories.journal %}
{% if entries %}
<ul>
{% for post in entries %}
  <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a>, {{ post.date | date: "%-d %B %Y" }}</li>
{% endfor %}
</ul>
{% else %}
<p>No entries yet.</p>
{% endif %}
