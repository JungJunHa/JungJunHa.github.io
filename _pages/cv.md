---
layout: page
permalink: /cv/
title: CV
nav: true
nav_order: 3
cv_pdf: /assets/pdf/Junha_Jung_CV.pdf
---

<div style="text-align: right; margin-bottom: 0.75rem;">
  <a href="{{ page.cv_pdf | relative_url }}" target="_blank" rel="noopener noreferrer">
    <i class="fa-solid fa-file-pdf"></i> Open / download PDF
  </a>
</div>

<iframe
  src="{{ page.cv_pdf | relative_url }}"
  title="Junha Jung CV"
  style="width: 100%; height: 85vh; min-height: 600px; border: 1px solid var(--global-divider-color); border-radius: 0.25rem;"
></iframe>
