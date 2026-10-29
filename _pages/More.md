---
layout: page
title: More
permalink: /projects/
description: 
nav: true
nav_order: 3
---

<h1 class="post-title">Data</h1>

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

### Publication in Chinese

1. 肖伟, **劳伟健**, 刘文翰, 贾昊文. "乡村创业：土地改革、减贫赋能与治理创新的视角". 载于 海闻 主编, 《田野变奏：农民生活变迁与乡村振兴》. 北京大学出版社, 2027.
2. [王剑程](https://isbf.sysu.edu.cn/zh-hans/teacher/288), **劳伟健**, [秦芳](https://riem.swufe.edu.cn/info/1231/11501.htm). 宗族文化与电商发展[J], 世界经济, 2026, 49(1): 111-142.
3. 晏正伟, **劳伟健**, [韩雷](https://business.xtu.edu.cn/index.jsp?cc=cshizidw&cd=teacher&ac=view&id=100175), 宋森安. 数字金融发展能够促进家庭捐赠吗[J], 经济学报, 2025, 12(1): 77-95.
<!-- 3. **劳伟健**，肖伟*. 农村集体产权制度改革与集体经济收入——基于CHFS数据的实证分析，外审。 -->

<style>
  .post-header {
    display: none;
  }

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
