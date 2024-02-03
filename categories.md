---
layout: page
permalink: /categories
title: Categories
---

<ul>
    {% for category in site.categories %}
        {% capture category_name %}{{ category | first }}{% endcapture %}
        <li>
            {{ category_name }}
        </li>
        {% for post in site.categories[category_name] %}
        <ul>
            <li>
                <span>{{- post.date | date: site.date_format -}}</span>
                <a href="{{ post.url | relative_url }}">{{ post.title | downcase }}</a>
            </li>
        </ul>
        {% endfor %}
    {% endfor %}
</ul>