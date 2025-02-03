---
# the default layout is 'page'
icon: fas fa-info-circle
order: 4
---

> Add Markdown syntax content to file `_tabs/about.md`{: .filepath } and it will show up on this page.
{: .prompt-tip }


/* Certifications Grid */
.certifications-grid {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    margin: 2rem 0;
  }
  
  /* Certification Card (Side-by-Side) */
  .certification-card {
    display: flex;          /* Flexbox layout */
    gap: 1.5rem;           /* Space between image and text */
    align-items: flex-start; /* Align items to top */
    background: var(--color-background);
    border: 1px solid var(--color-border);
    border-radius: 8px;
    padding: 1.5rem;
    transition: transform 0.2s;
  }
  
  /* Force small badge size */
  .cert-badge {
    width: 80px !important;  /* Force small size */
    height: 80px !important; /* Override any other styles */
    object-fit: contain;     /* Prevent stretching */
    flex-shrink: 0;         /* Prevent image from shrinking */
  }
  
  /* Text content takes remaining space */
  .cert-content {
    flex-grow: 1;
  }
  
  /* Hover effect */
  .certification-card:hover {
    transform: translateY(-3px);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  }

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