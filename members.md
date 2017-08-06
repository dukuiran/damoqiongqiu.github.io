---
layout: page
title: ""
permalink: /members/
---

<ul>
    {% for member in site.data.members %}
    <li>
        <a href="https://github.com/{{ member.github }}" target="_blank">
        {{ member.name }}
        </a>
    </li>
    {% endfor %}
</ul>