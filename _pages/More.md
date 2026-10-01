---
layout: page
title: More
permalink: /projects/
description: 
nav: true
nav_order: 3
---

{% assign sorted_projects = site.projects | sort: "importance" %}
<div class="more-list">
{% for project in sorted_projects %}
  <div class="more-item">
    <div class="more-item-line">
      <strong>{{ project.title }}</strong>
      <a href="{{ project.redirect }}" target="_blank" rel="noopener noreferrer">Website</a>
      <span class="more-item-role">{{ project.role }}</span>
    </div>
    <details>
      <summary>About this project</summary>
      <p>{{ project.description }}</p>
    </details>
  </div>
{% endfor %}
</div>

<style>
  body, p, li, h1, .navbar-brand, .post-title {
    font-family: Georgia, 'Times New Roman', Times, serif !important;
  }

  .more-item {
    padding: 0.75rem 0;
    border-bottom: 1px solid var(--global-divider-color);
  }

  .more-item-line {
    display: flex;
    align-items: baseline;
    gap: 0.75rem;
    flex-wrap: wrap;
  }

  .more-item-role {
    color: var(--global-text-color-light);
  }

  .more-item details {
    margin-top: 0.4rem;
  }

  .more-item summary {
    width: fit-content;
    color: var(--global-theme-color);
    cursor: pointer;
  }

  .more-item p {
    margin: 0.5rem 0 0;
    max-width: 48rem;
  }
</style>
