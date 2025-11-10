---
layout: page
title: "Projects"
---

<div class="grid">
{% for p in site.data.projects %}
  <article class="card" aria-labelledby="p{{ forloop.index }}-title">
    <div class="body">
      <h3 id="p{{ forloop.index }}-title">{{ p.title }}</h3>
      {% if p.tags %}<p class="meta">{{ p.tags | join: ' • ' }}</p>{% endif %}
      <p>{{ p.blurb }}</p>
      <p class="repo-link">
        {% if p.repo and p.repo != 'private' and p.repo != '' %}
          <a href="{{ p.repo }}" target="_blank" rel="noopener">Repository ↗</a>
        {% else %}
          <span class="private-label">Private</span>
        {% endif %}
      </p>
    </div>
  </article>
{% endfor %}
</div>
