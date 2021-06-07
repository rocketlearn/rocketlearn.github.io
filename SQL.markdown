---
layout: page
title: SQL
permalink: /sql/
weight: 4
category: SQL
---

{% assign pagelist = site.posts|where: 'category',page.category %}
{%- if pagelist.size > 0 -%}
    <div>
    <h2 class="post-list-heading">{{ page.list_title | default: "" }}</h2>
    <ul class="post-list">
      {%- for post in pagelist -%}
      <li>
        {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
        <span class="post-meta">{{ post.date | date: date_format }}</span>
        <h3>
          <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
          </a>
        </h3>
        {%- if site.show_excerpts -%}
          {{ post.excerpt }}
        {%- endif -%}
      </li>
      {%- endfor -%}
    </ul>
    </div>
{% endif%}