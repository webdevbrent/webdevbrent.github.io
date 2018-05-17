---
layout: demo
---

<ul>
  {% for demo in site.demos %}
    <li>
      <a href="{{ demo.url }}">{{ demo.title }}</a>
      - {{ demo.img }}
    </li>
  {% endfor %}
</ul>