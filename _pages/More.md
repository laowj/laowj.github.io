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
  <details class="more-item">
    <summary>
      <span class="more-item-line">
        <span>[{{ project.number }}]</span>
        <strong><a href="{{ project.redirect }}" target="_blank" rel="noopener noreferrer">{{ project.title }}</a></strong>
        <span class="more-item-role">— {{ project.role }}</span>
      </span>
      <span class="more-item-toggle" aria-hidden="true"></span>
    </summary>
    <div class="more-item-description">
      <p>{{ project.description }}</p>
    </div>
  </details>
{% endfor %}
</div>

<style>
  body, p, li, h1, .navbar-brand, .post-title {
    font-family: Georgia, 'Times New Roman', Times, serif !important;
  }

  .more-item {
    border-bottom: 1px solid var(--global-divider-color);
  }

  .more-item summary {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 1rem;
    padding: 1.25rem 0.5rem;
    cursor: pointer;
    list-style: none;
  }

  .more-item summary::-webkit-details-marker {
    display: none;
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

  .more-item-toggle {
    display: grid;
    width: 3rem;
    height: 3rem;
    flex: 0 0 3rem;
    place-items: center;
    border-radius: 50%;
    background: rgba(128, 128, 128, 0.08);
  }

  .more-item-toggle::before {
    width: 0.65rem;
    height: 0.65rem;
    content: "";
    border-right: 2px solid currentColor;
    border-bottom: 2px solid currentColor;
    transform: translateY(-0.15rem) rotate(45deg);
    transition: transform 0.2s ease;
  }

  .more-item[open] .more-item-toggle::before {
    transform: translateY(0.15rem) rotate(225deg);
  }

  .more-item-description {
    padding: 0 4.5rem 1.25rem 0.5rem;
  }

  .more-item p {
    margin: 0;
    max-width: 48rem;
  }

  @media (max-width: 576px) {
    .more-item summary {
      padding: 1rem 0;
    }

    .more-item-toggle {
      width: 2.5rem;
      height: 2.5rem;
      flex-basis: 2.5rem;
    }

    .more-item-description {
      padding: 0 0 1rem;
    }
  }
</style>
