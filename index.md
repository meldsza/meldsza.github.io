---
layout: page
title: 'Home'
permalink: /
---
{% for post in site.posts %}

    <h2>{{post.title}}</h2>
    <code>{{ post.content }}</code>

{% endfor %}
