---
layout: archive
title: ""
permalink: /publications/
author_profile: true
---

{% include base_path %}
{% assign papers = site.publications | sort: "date" | reverse %}

{% if site.author.googlescholar %}
<p>
  Below is a list of my peer-reviewed publications, ordered from newest
  to oldest, with my name in **bold**. Citation metrics are available on
  <a href="{{ site.author.googlescholar }}">my Google Scholar Profile</a>.
</p>
{% endif %}

<div class="publication-filters" aria-label="Filter publications by year">
  <button type="button" data-year="all" aria-pressed="true">All</button>
  {% assign previous_year = "" %}
  {% for post in papers %}
    {% assign year = post.date | date: "%Y" %}
    {% if year != previous_year %}
      <button type="button" data-year="{{ year }}" aria-pressed="false">
        {{ year }}
      </button>
      {% assign previous_year = year %}
    {% endif %}
  {% endfor %}
</div>

<div class="publication-list">
  {% for post in papers %}
  <article class="publication-row" data-year="{{ post.date | date: '%Y' }}">
    <div class="publication-year">{{ post.date | date: "%Y" }}</div>
    <div class="publication-details">
      <div class="publication-venue">{{ post.venue | escape }}</div>
      <h2>{{ post.title | escape }}</h2>

      {% if post.authors %}
      <div class="publication-authors">
        {{ post.authors | markdownify }}
      </div>
      {% elsif post.citation %}
      <div class="publication-authors">
        {{ post.citation | markdownify }}
      </div>
      {% endif %}

      {% if post.paperurl %}
      <a class="publication-paper" href="{{ post.paperurl }}">Read paper ↗</a>
      {% endif %}
    </div>
  </article>
  {% endfor %}
</div>

<style>
.publication-authors strong {
  font-family: "Lato-Bold", "Lato", Arial, sans-serif;
  font-weight: 700;
}  
.publication-filters {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin: 24px 0;
}
.publication-filters button {
  margin: 0;
  padding: 6px 14px;
  border: 1px solid #ddd;
  border-radius: 20px;
  background: white;
  color: #494e52;
  font: inherit;
  font-size: 0.8em;
  cursor: pointer;
}
.publication-filters button[aria-pressed="true"] {
  background: #d94200;
  border-color: #d94200;
  color: white;
}
.publication-row {
  display: grid;
  grid-template-columns: 60px minmax(0, 1fr);
  gap: 20px;
  padding: 24px 0;
  border-bottom: 1px solid #e5e5e5;
}
.publication-row[hidden] {
  display: none;
}
.publication-year {
  color: #d94200;
  font-weight: bold;
}
.publication-venue {
  color: #666;
  font-size: 0.75em;
  letter-spacing: 0.04em;
  text-transform: uppercase;
}
.publication-details h2 {
  margin: 6px 0 10px;
  padding: 0;
  border: 0;
  font-size: 1.1em;
  line-height: 1.4;
}
.publication-details h2 a {
  color: #494e52;
  text-decoration: none;
}
.publication-details h2 a:hover {
  color: #d94200;
}
.publication-authors {
  font-size: 0.85em;
  line-height: 1.6;
}
.publication-authors p {
  margin: 0 0 10px;
}
.publication-paper {
  font-size: 0.8em;
  color: #d94200;
}
@media (max-width: 600px) {
  .publication-row {
    grid-template-columns: 1fr;
    gap: 8px;
  }
}
</style>

<script>
document.querySelectorAll(".publication-filters button").forEach(button => {
  button.addEventListener("click", () => {
    const year = button.dataset.year;
    document.querySelectorAll(".publication-filters button").forEach(item => {
      item.setAttribute("aria-pressed", String(item === button));
    });
    document.querySelectorAll(".publication-row").forEach(row => {
      row.hidden = year !== "all" && row.dataset.year !== year;
    });
  });
});
</script>
