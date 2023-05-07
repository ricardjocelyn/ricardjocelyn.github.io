---
layout: page
permalink: /press/
title: press
description: Press. 
nav: true
nav_order: 5
---

<!-- pages/press.md -->
<div class="press">
{%- if site.enable_press_categories and page.display_categories %}
  <!-- Display categorized  press -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_ppress = site.press | where: "category", category -%}
  {%- assign sorted_press = categorized_press | sort: "importance" %}
  <!-- Generate cards for each press -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for press in sorted_press -%}
      {% include press_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for press in sorted_press -%}
      {% include press.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display press without categories -->
  {%- assign sorted_press = site.press | sort: "importance" -%}
  <!-- Generate cards for each press -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for press in sorted_press -%}
      {% include press_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for press in sorted_press -%}
      {% include press.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>



1. Yale University Press: https://medicine.yale.edu/psychiatry/news-article/confronting-racially-exclusionary-practices-in-the-acquisition-and-analyses-of-neuroimaging-data/
2. USA Today: https://www.usatoday.com/story/news/health/2022/04/07/magic-mushrooms-linked-decreased-risk-opioid-addiction-study/9469652002/
3. Time Magazine: https://time.com/6167638/psilocybin-addiction-therapeutic-breakthrough/
