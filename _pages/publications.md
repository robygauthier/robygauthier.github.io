---
layout: page
permalink: /publications/
title: Publications
description:
years: [2022, 2021, 2020, 2019, 2018, 2017, 2013]
nav: true
nav_order: 1
---
<!-- _pages/publications.md -->
Here are a list of all my scientific publications. You can also access those papers on my google scholar [here](https://scholar.google.com/citations?hl=en&user=Tv6LOuUAAAAJ&view_op=list_works&sortby=pubdate).

<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
