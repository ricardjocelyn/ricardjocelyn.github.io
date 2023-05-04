---
layout: page
title: press 
permalink: /press/
description: A growing collection of your cool press.
nav: true
nav_order: 2
display_categories: [work, fun]
horizontal: false
---

<!-- pages/press.md -->
<div class="press">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized press -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_press = site.press | where: "category", category -%}
  {%- assign sorted_press = categorized_press | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_press -%}
      {% include press_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_press -%}
      {% include press.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display press without categories -->
  {%- assign sorted_press = site.press | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_press -%}
      {% include press_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_press -%}
      {% include press.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
