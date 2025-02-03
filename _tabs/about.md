---
layout: page
icon: fas fa-info-circle
order: 4
extra_css: "/assets/css/certifications.css"
---


## Certifications

<div class="certifications-grid">
  {% for cert in site.data.certifications %}
  <div class="certification-card">
    <!-- Left: Badge -->
    <img src="{{ cert.badge | relative_url }}" alt="{{ cert.alt }}" class="cert-badge">
    <!-- Right: Content -->
    <div class="cert-content">
      <h3>{{ cert.title }}</h3>
      <p class="cert-issuer">Issued by {{ cert.issuer }}</p>
      <p class="cert-date">{{ cert.date }}</p>
      <div class="cert-links">
        {% if cert.verify_url %}
          <a href="{{ cert.verify_url }}" target="_blank">
            <i class="fas fa-external-link-alt"></i> Verify
          </a>
        {% endif %}
      </div>
    </div>
  </div>
  {% endfor %}
</div>