---
# the default layout is 'page'
icon: fas fa-info-circle
order: 4
---

> Add Markdown syntax content to file `_tabs/about.md`{: .filepath } and it will show up on this page.
{: .prompt-tip }

## Certifications

{% for cert in site.data.certifications %}
<div class="certification-block">
  <h3>{{ cert.title }}</h3>
  <p><strong>Issuer:</strong> {{ cert.issuer }}</p>
  <p><strong>Date:</strong> {{ cert.date }}</p>
  {% if cert.verify_url %}
    <a href="{{ cert.verify_url }}">Verify</a>
  {% endif %}
  {% if cert.pdf %}
    | <a href="{{ cert.pdf }}">PDF</a>
  {% endif %}
  {% if cert.badge %}
    <img src="{{ cert.badge }}" alt="{{ cert.title }} Badge" width="100">
  {% endif %}
</div>
{% endfor %}