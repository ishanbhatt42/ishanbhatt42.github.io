---
title: Writing
layout: archive
classes: wide
permalink: /writing/
author_profile: true
---

{% assign writing_sorted = site.writing | sort: 'date' | reverse %}
<ul class="writing-list">
{% for post in writing_sorted %}
  <li class="writing-card">
    <a class="writing-card__link" href="{{ post.url | relative_url }}">
      {% if post.header.teaser %}
        <div class="writing-card__image">
          <img src="{{ post.header.teaser | relative_url }}" alt="">
        </div>
      {% endif %}
      <div class="writing-card__body">
        <h2 class="writing-card__title">{{ post.title }}</h2>
        {% if post.excerpt %}<p class="writing-card__subtitle">{{ post.excerpt | markdownify | strip_html }}</p>{% endif %}
        <p class="writing-card__date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time></p>
      </div>
    </a>
  </li>
{% endfor %}
</ul>
