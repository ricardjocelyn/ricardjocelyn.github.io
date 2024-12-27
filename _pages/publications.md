---
layout: page
permalink: /publications/
title: publications
description: 
years: [2024, 2023, 2022, 2021, 2020, 2019]
nav: true
nav_order: 1
---
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>

---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---
<!--
 {% if site.author.googlescholar %}
  <div class="wordwrap">You can also find my articles on <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</div>
 {% endif %}
-->

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}

[Title)
======
**December 27th, 2024**
<div style="text-align: center;">
</div>
<br>
This article ...
<br>
<br>
**Recommended citation:**
<br>
