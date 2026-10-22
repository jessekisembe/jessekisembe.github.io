---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
header:
  text_color: $dark-gray
---

{% include base_path %}

<!--
See my [full](../../files/schwarzwald_cv_full.pdf) or [efficient](../../files/schwarzwald_cv.pdf) CV. 
-->

Education
======
* Ph.D. in Geography (Concentration in Climate Science), University of Florida, 2027 (expected) 
* Master of Science in Disaster Risk Management, Makerere University, 2021
* Bachelor of Science in Meteorology, Makerere University, 2017

Selected Publications
=====
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
