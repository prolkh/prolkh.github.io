---
layout: page
permalink: /tags
title: tags
---

<ul>
    {% for tag in site.tags %}
        {% capture tag_name %}{{ tag | first }}{% endcapture %}
        <li>
            {{ tag_name }}
        </li>
        {% for post in site.tags[tag_name] %}
        <ul>
            <li>
                <span>{{- post.date | date: site.date_format -}}</span>
                <a href="{{ post.url | relative_url }}">{{ post.title | downcase }}</a>
            </li>
        </ul>
        {% endfor %}
    {% endfor %}
</ul>