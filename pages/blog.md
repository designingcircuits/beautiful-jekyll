---
layout: page
title: Blog Posts
use-site-title: true
permalink: /blog/
---

<section class="archive-post-list">

   {% for post in site.posts %}
       {% assign currentDate = post.date | date: "%Y" %}
       {% if currentDate != myDate %}
           {% unless forloop.first %}</ul>{% endunless %}
           <h1 class="fix">{{ currentDate }}</h1>
           <ul>
           {% assign myDate = currentDate %}
       {% endif %}
       <li class="fix"><a href="{{ post.url }}"><span>{{ post.date | date: "%B %-d" }}</span> - {{ post.title }}</a>
       <!-- : {{ post.excerpt | strip_html | xml_escape | truncatewords: site.excerpt_length }} -->
       </li>
       {% if forloop.last %}</ul>{% endif %}
   {% endfor %}

</section>
