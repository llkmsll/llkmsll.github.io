---
layout: page
permalink: /algorithm/
title: algorithm
description: C++ 알고리즘 문제풀이
---

<ul class="algorithm-list">
{% for algorithm in site.algorithm %}
    <li>
        <h2><a class="algorithm-title" href="{{ algorithm.url | prepend: site.baseurl }}">{{ algorithm.title }}</a></h2>
        <p class="post-meta">{{ algorithm.date | date: '%B %-d, %Y — %H:%M' }}</p>
    </li>
{% endfor %}
</ul>