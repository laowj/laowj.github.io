---
layout: page
title: More
permalink: /projects/
description: 
nav: true
nav_order: 3
---

<h2 class="more-section-title">Data</h2>

{% assign sorted_projects = site.projects | sort: "importance" %}
<ol class="more-list">
{% for project in sorted_projects %}
  <li>
    <details class="more-item">
      <summary>
        <span class="more-item-line">
          <strong><a href="{{ project.redirect }}" target="_blank" rel="noopener noreferrer">{{ project.title }}</a></strong>
          <span class="more-item-role">— {{ project.role }}</span>
        </span>
      </summary>
      <div class="more-item-description">
        <p>{{ project.description }}</p>
      </div>
    </details>
  </li>
{% endfor %}
</ol>

<h2 class="more-section-title">Publication in Chinese</h2>

<div class="more-publication-list" markdown="1">

1. 肖伟, **劳伟健**, 刘文翰, 贾昊文. "乡村创业：土地改革、减贫赋能与治理创新的视角". 载于 海闻 主编, 《田野变奏：农民生活变迁与乡村振兴》. 北京大学出版社, 2027.
2. [王剑程](https://isbf.sysu.edu.cn/zh-hans/teacher/288), **劳伟健**, [秦芳](https://riem.swufe.edu.cn/info/1231/11501.htm). 宗族文化与电商发展[J], 世界经济, 2026, 49(1): 111-142.
3. 晏正伟, **劳伟健**, [韩雷](https://business.xtu.edu.cn/index.jsp?cc=cshizidw&cd=teacher&ac=view&id=100175), 宋森安. 数字金融发展能够促进家庭捐赠吗[J], 经济学报, 2025, 12(1): 77-95.
<!-- 3. **劳伟健**，肖伟*. 农村集体产权制度改革与集体经济收入——基于CHFS数据的实证分析，外审。 -->

</div>

<style>
  .post-header {
    display: none;
  }

  body, p, li, ol, ul, h2, .navbar-brand, .more-section-title {
    font-family: Georgia, 'Times New Roman', Times, serif !important;
  }

  body, p, li, ol, ul {
    font-weight: normal !important;
  }

  .more-section-title {
    margin: 1.5rem 0 0.75rem;
    font-size: 1.25rem !important;
    font-weight: bold !important;
  }

  .more-list + .more-section-title {
    margin-top: 2.5rem;
  }

  .more-list > li,
  .more-publication-list li {
    padding: 0.65rem 0;
    border-bottom: 1px solid var(--global-divider-color);
  }

  .more-list,
  .more-publication-list ol {
    margin: 0;
    padding-left: 2rem;
  }

  .more-list {
    width: calc(100% - 1.75rem);
    margin-left: 1.75rem;
  }

  .more-item summary {
    display: flex;
    align-items: baseline;
    justify-content: space-between;
    gap: 1rem;
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

  .more-item summary::after {
    width: 0.55rem;
    height: 0.55rem;
    flex: 0 0 0.55rem;
    content: "";
    border-right: 2px solid currentColor;
    border-bottom: 2px solid currentColor;
    transform: translateY(-0.15rem) rotate(45deg);
    transition: transform 0.2s ease;
  }

  .more-item[open] summary::after {
    transform: translateY(0.15rem) rotate(225deg);
  }

  .more-item p {
    max-width: 52rem;
    margin: 0.65rem 1.5rem 0.85rem 0;
    color: var(--global-text-color-light);
    line-height: 1.55;
    text-align: justify;
    text-justify: inter-word;
    hyphens: auto;
  }
</style>
