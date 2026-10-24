---
layout: archive
title: "News Archive"
permalink: /news/
author_profile: true
redirect_from:
  - /press/
---

<p class="news-intro">All News</p>

<div class="jk-news-list">

  <a class="jk-news-item" href="https://blog.chc.ucsb.edu/?p=1997">
    <div class="jk-news-content">
      <span class="jk-news-meta">
        June 24, 2026
      </span>
      <h2>Looking beyond seasonal rainfall totals</h2>
      <p>
        The Climate Hazards Center features my research on how
        East Africa's rainy seasons are changing and why rainfall
        timing, frequency, and intensity matter.
      </p>
    </div>
    <span class="jk-news-arrow" aria-hidden="true">→</span>
  </a>

  <a class="jk-news-item"
     href="https://news.clas.ufl.edu/uf-doctoral-students-honored-with-nasa-finesst-award/">
    <div class="jk-news-content">
      <span class="jk-news-meta">
        November 18, 2025
      </span>
      <h2>NASA FINESST Award supports dry-spell research</h2>
      <p>
        UF highlights my selection for a NASA FINESST fellowship
        to investigate dry spell events in the Horn of Africa.
      </p>
    </div>
    <span class="jk-news-arrow" aria-hidden="true">→</span>
  </a>

</div>

<style>
.news-intro {
  color: #666;
  margin-bottom: 1.5rem;
}

.jk-news-list {
  border-top: 1px solid #ddd;
}

.jk-news-list .jk-news-item {
  display: grid;
  grid-template-columns: minmax(0, 1fr) 28px;
  gap: 24px;
  align-items: center;
  padding: 28px 12px;
  border-bottom: 1px solid #ddd;
  color: #494e52;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.jk-news-meta {
  display: block;
  color: #666;
  font-size: 0.72rem;
  letter-spacing: 0.04em;
  text-transform: uppercase;
}

.jk-news-item h2 {
  margin: 8px 0 10px;
  padding: 0;
  border: 0;
  font-family: "Lato-Bold", "Lato", Arial, sans-serif;
  font-size: 1.15rem;
  line-height: 1.35;
  color: #494e52;
}

.jk-news-item p {
  margin: 0;
  font-size: 0.9rem;
  line-height: 1.6;
}

.jk-news-arrow {
  color: #d94200;
  font-size: 1.5rem;
  transition: transform 0.2s ease;
}

.jk-news-item:hover,
.jk-news-item:focus-visible {
  background-color: #fff7f2;
}

.jk-news-item:hover h2,
.jk-news-item:focus-visible h2 {
  color: #d94200;
}

.jk-news-item:hover .jk-news-arrow {
  transform: translateX(4px);
}

.jk-news-item:focus-visible {
  outline: 2px solid #d94200;
  outline-offset: 3px;
}

@media (max-width: 600px) {
  .jk-news-list .jk-news-item {
    gap: 12px;
    padding: 22px 4px;
  }
}
</style>
