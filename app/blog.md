---
layout: layout.njk
title: Blog | A random collection of tech thinkings from over the years
---

# Blog
A random collection of tech thinkings from over the years. I'm bad at regular updates and some of these thoughts may not have aged well.

<ul>
{%- for page in collections.blog -%}
<li>
{{ page.data.title }}
</li>
{%- endfor -%}
</ul>
