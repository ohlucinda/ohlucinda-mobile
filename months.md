---
layout: default
title: Months
permalink: /months/
---

<div style="margin-top: -40px;">

  <div class="months-back">
    <a href="{{ '/' | relative_url }}">
      &lt; back
    </a>
  </div>

  <header class="site-header" style="margin-bottom: 20px;">
    Months
  </header>

  {% assign posts_by_month = site.posts | group_by_exp: "post", "post.date | date: '%B %Y'" %}

  <div class="writes-index">
    {% for group in posts_by_month reversed %}
    <details class="months-page-details">
      <summary>{{ group.name }}</summary>
      {% assign sorted_posts = group.items | reverse %}
      {% for post in sorted_posts %}
        <div>
          <a href="{{ post.url | relative_url }}">
            {{ post.title }}
          </a>
        </div>
      {% endfor %}
    </details>
    {% endfor %}
  </div>

</div>
