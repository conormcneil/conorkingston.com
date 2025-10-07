---
layout: default
title: case studies
permalink: /case_studies/
exclude_from_list: true
---

<section class="container my-5">
    <h2>{{ page.title }}</h2>

    {% for case in site.case_studies %}
        {% unless case.exclude_from_list %}
            {% include card-link.html
            url=case.url
            title=case.title
            date=case.date
            text=case.summary
            %}
        {% endunless %}
    {% endfor %}
</section>