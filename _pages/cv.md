---
layout: page
permalink: /cv/
title: CV
nav: true
nav_order: 5
---

<!-- To update the CV, replace assets/pdf/cv.pdf with the new PDF (keep the same file name) and push. -->

<div class="mb-3">
  <a class="btn btn-sm z-depth-0" role="button" href="{{ '/assets/pdf/cv.pdf' | relative_url }}?v={{ site.time | date: '%s' }}" target="_blank" rel="noopener noreferrer">
    <i class="fa-solid fa-file-pdf"></i> Download CV (PDF)
  </a>
</div>

<object data="{{ '/assets/pdf/cv.pdf' | relative_url }}?v={{ site.time | date: '%s' }}" type="application/pdf" width="100%" style="height: 90vh; min-height: 600px;">
  <p>Your browser cannot display the PDF here. <a href="{{ '/assets/pdf/cv.pdf' | relative_url }}?v={{ site.time | date: '%s' }}">Download the CV</a> instead.</p>
</object>
