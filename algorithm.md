---
layout: page
permalink: /algorithm/
title: algorithm
description: C++ 알고리즘 문제 풀이
---

<ul class="algorithm-list">
{% for solve in site.algorithm %}
    <li>
        <h2><a class="algorithm-title" href="{{ solve.url | prepend: site.baseurl }}">{{ solve.title }}</a></h2>
        <p class="post-meta">{{ solve.date | date: '%B %-d, %Y — %H:%M' }}</p>
    </li>
{% endfor %}
</ul>