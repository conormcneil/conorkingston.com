---
layout: default
title: Blog
permalink: /blog/
exclude_from_list: true
---

<section class="container my-5">
    <h2>{{ page.title }}</h2>

    {% for post in site.posts %}
        {% unless post.exclude_from_list %}
            {% include card-link.html
            url=post.url
            title=post.title
            date=post.date
            text=post.summary
            %}
        {% endunless %}
    {% endfor %}
</section>