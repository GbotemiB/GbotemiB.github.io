---
layout: page
permalink: /cv/
title: cv
nav: true
nav_order: 5
---

{% capture cv_exists %}{% file_exists assets/pdf/cv.pdf %}{% endcapture %}
{% capture cv_full_exists %}{% file_exists assets/pdf/cv_full.pdf %}{% endcapture %}

{% if cv_exists == "true" %}

<div class="mb-3">
  <a class="btn btn-sm z-depth-0" role="button" href="{{ '/assets/pdf/cv.pdf' | relative_url }}" target="_blank" rel="noopener noreferrer">
    <i class="fa-solid fa-file-pdf"></i> Resume (1 page)
  </a>
  {% if cv_full_exists == "true" %}
  <a class="btn btn-sm z-depth-0" role="button" href="{{ '/assets/pdf/cv_full.pdf' | relative_url }}" target="_blank" rel="noopener noreferrer">
    <i class="fa-solid fa-file-pdf"></i> Full CV (3 pages)
  </a>
  {% endif %}
</div>

<object data="{{ '/assets/pdf/cv.pdf' | relative_url }}" type="application/pdf" width="100%" style="height: 90vh; min-height: 600px;">
  <p>Your browser cannot display the PDF here. <a href="{{ '/assets/pdf/cv.pdf' | relative_url }}">Download the resume</a> instead.</p>
</object>

{% else %}

A PDF version of my Curriculum Vitae will be available here soon.

{% endif %}
