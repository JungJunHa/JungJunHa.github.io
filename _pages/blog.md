---
layout: default
permalink: /blog/
title: news
nav: true
nav_order: 2
---

<style>
  .news-list {
    margin: 0 0 40px;
    padding: 0;
    list-style: none;
  }
  .news-list li {
    list-style: none;
  }
  .news-list .news-year {
    padding-bottom: 0.4rem;
    border-bottom: 1px solid var(--global-divider-color);
  }
  .news-list .news-year h2 {
    margin: 0;
    font-weight: 700;
  }
  .news-list .news-year:not(:first-child) {
    margin-top: 3.5rem;
  }
  .news-list .news-item {
    display: flex;
    gap: 1.75rem;
    align-items: flex-start;
    padding: 2rem 0;
    scroll-margin-top: 4rem;
    border-bottom: 1px solid var(--global-divider-color);
  }
  .news-list .news-item:has(+ .news-year),
  .news-list .news-item:last-child {
    border-bottom: none;
  }
  .news-list .news-thumb {
    flex: 0 0 220px;
    width: 220px;
    aspect-ratio: 4 / 3;
    object-fit: cover;
    border-radius: 0.25rem;
  }
  .news-list .news-body {
    flex: 1;
    min-width: 0;
  }
  .news-list .news-body h3 {
    margin: 0;
  }
  .news-list .news-date {
    margin: 0.25rem 0 0;
    font-size: 0.875rem;
    color: var(--global-text-color-light);
  }
  .news-list .news-content {
    margin-top: 1rem;
  }
  .news-list .news-content > :last-child {
    margin-bottom: 0;
  }
  @media (max-width: 576px) {
    .news-list .news-item {
      gap: 1rem;
    }
    .news-list .news-thumb {
      flex-basis: 110px;
      width: 110px;
    }
  }
</style>

<div class="post">
  <ul class="news-list">
    {% for post in site.posts %}
      {% assign year = post.date | date: '%Y' %}
      {% if year != current_year %}
        {% assign current_year = year %}
        <li class="news-year"><h2>{{ year }}</h2></li>
      {% endif %}

      {% assign thumb = post.thumbnail | default: 'assets/img/9.jpg' %}
      <li class="news-item" id="{{ post.slug }}">
        <img class="news-thumb" src="{{ thumb | relative_url }}" alt="{{ post.title }}" loading="lazy">
        <div class="news-body">
          <h3>{{ post.title }}</h3>
          <p class="news-date">{{ post.date | date: '%B %Y' }}</p>
          <div class="news-content">{{ post.content }}</div>
        </div>
      </li>
    {% endfor %}
  </ul>
</div>
