---
layout: page
title: Reports
permalink: /reports/
---

Periodic reviews of the desk

{% assign entries = site.categories.reports %}
{% if entries %}
<ul>
{% for post in entries %}
  <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a>, {{ post.date | date: "%-d %B %Y" }}</li>
{% endfor %}
</ul>
{% else %}
<p> what was traded, what the rules did, and what changed.:No reports yet.</p>
{% endif %}
