---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from:
  - /home/
  - /home.html
---

<nav class="home-section-nav" aria-label="Homepage sections">
  <a href="#introduction" aria-current="location">
    <span class="section-label">Introduction</span>
    <span class="section-dot" aria-hidden="true"></span>
  </a>
  <a href="#research">
    <span class="section-label">Research</span>
    <span class="section-dot" aria-hidden="true"></span>
  </a>
  <a href="#recent-news">
    <span class="section-label">News</span>
    <span class="section-dot" aria-hidden="true"></span>
  </a>
</nav>

<section id="introduction" class="home-section" markdown="1">

## About Me

I'm a climate scientist studying intraseasonal rainfall variability to help inform agricultural decision-making. I'm currently a Ph.D. Candidate in the [Department of Geography](https://geog.ufl.edu/) at the University of Florida, working with [Berry Wen](https://www.stonybrook.edu/somas/people/faculty/berry-wen.html) (now at Stony Brook University).

</section>

<section id="research" class="home-section" markdown="1">

## Research

My doctoral work is motivated by a simple question: **What matters most for livelihoods, the total amount of rain a season brings or when, how often, and how intensely it falls?** I've [found](https://doi.org/10.1175/JHM-D-25-0080.1) that examining seasonal rainfall totals together with rainfall timing, frequency, and intensity gives a fuller picture of how rainy seasons are changing across East Africa. I've also shown that understanding how the rainy season onset relates to other rainfall characteristics within the season can help us understand how the season is likely to unfold.

[Explore my publications →]({{ '/publications/' | relative_url }})

</section>

<section id="recent-news" class="home-section">
  <h2>Recent News</h2>

  <div class="home-news-list">
    <a class="home-news-row"
       href="{{ '/news/2026-06-24/' | relative_url }}">
      <div>
        <span class="home-news-date">
          June 24, 2026
        </span>
        <h3>Looking beyond seasonal rainfall totals</h3>
        <p>
          The UCSB Climate Hazards Center features our research
          on how East Africa’s rainy seasons are changing.
        </p>
      </div>
      <span class="home-news-arrow" aria-hidden="true">→</span>
    </a>

    <a class="home-news-row"
       href="{{ '/news/nasa-finesst/' | relative_url }}">
      <div>
        <span class="home-news-date">
          November 18, 2025
        </span>
        <h3>Jesse Kisembe receives a NASA FINESST Award</h3>
        <p>
          I received funding for my proposal on "**Delineating and Characterizing Dry Spell Events in the Horn of Africa**" 
        </p>
      </div>
      <span class="home-news-arrow" aria-hidden="true">→</span>
    </a>
  </div>

  <p class="home-Read-More-News">
    <a href="{{ '/news/' | relative_url }}">Read More News →</a>
  </p>
</section>

<style>
.home-section {
  margin-bottom: 2.5rem;
  scroll-margin-top: 100px;
}

.home-section > h2 {
  margin-top: 0;
}

.home-section-nav {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  margin-bottom: 2rem;
}

.home-section-nav a {
  display: flex;
  align-items: center;
  gap: 10px;
  color: #666;
  text-decoration: none;
  font-size: 0.8rem;
}

.section-dot {
  display: block;
  width: 9px;
  height: 9px;
  border: 1px solid currentColor;
  border-radius: 50%;
  flex-shrink: 0;
}

.home-section-nav a[aria-current="location"] {
  color: #d94200;
  font-family: "Lato-Bold", "Lato", Arial, sans-serif;
}

.home-section-nav a[aria-current="location"] .section-dot {
  background: #d94200;
  box-shadow: 0 0 0 3px rgba(217, 66, 0, 0.12);
}

.home-section-nav a:focus-visible,
.home-news-row:focus-visible {
  outline: 2px solid #d94200;
  outline-offset: 4px;
}

/* Reserve space for the right-side navigation on wide screens. */
@media (min-width: 1200px) {
  body:has(.home-section-nav) #main {
    padding-right: 160px;
  }

  .home-section-nav {
    position: fixed;
    right: 20px;
    top: 50%;
    transform: translateY(-50%);
    flex-direction: column;
    align-items: flex-end;
    gap: 8px;
    margin: 0;
    z-index: 15;
  }

  .home-section-nav a {
    justify-content: flex-end;
    min-height: 44px;
    padding: 0 4px;
  }
}

.home-news-list {
  border-top: 1px solid #ddd;
}

.page__content a.home-news-row {
  display: grid;
  grid-template-columns: minmax(0, 1fr) 24px;
  align-items: center;
  gap: 20px;
  padding: 24px 8px;
  border-bottom: 1px solid #ddd;
  color: #494e52;
  text-decoration: none;
}

.home-news-date {
  color: #666;
  font-size: 0.72rem;
  letter-spacing: 0.03em;
  text-transform: uppercase;
}

.home-news-row h3 {
  margin: 8px 0;
  font-size: 1.1rem;
  line-height: 1.4;
}

.page__content .home-news-row p {
  margin: 0;
  font-size: 0.9rem;
  line-height: 1.6;
}

.home-news-arrow {
  color: #d94200;
  font-size: 1.4rem;
}

.home-news-row:hover {
  background: #fff7f2;
}

.home-news-row:hover h3 {
  color: #d94200;
}

.home-all-news {
  margin-top: 1.2rem;
}
</style>

<script>
(function () {
  const nav = document.querySelector(".home-section-nav");
  if (!nav) return;

  const links = Array.from(nav.querySelectorAll('a[href^="#"]'));
  const sections = links.map(link =>
    document.getElementById(link.getAttribute("href").slice(1))
  );

  function setActive(id) {
    links.forEach(link => {
      if (link.getAttribute("href") === "#" + id) {
        link.setAttribute("aria-current", "location");
      } else {
        link.removeAttribute("aria-current");
      }
    });
  }

  function updateActiveSection() {
    const marker = Math.min(180, window.innerHeight * 0.3);
    let active = sections[0];

    sections.forEach(section => {
      if (section && section.getBoundingClientRect().top <= marker) {
        active = section;
      }
    });

    const atBottom =
      window.scrollY + window.innerHeight >=
      document.documentElement.scrollHeight - 4;

    if (atBottom) active = sections[sections.length - 1];
    if (active) setActive(active.id);
  }

  let scheduled = false;
  window.addEventListener("scroll", function () {
    if (scheduled) return;
    scheduled = true;
    requestAnimationFrame(function () {
      updateActiveSection();
      scheduled = false;
    });
  }, { passive: true });

  window.addEventListener("resize", updateActiveSection);
  window.addEventListener("load", updateActiveSection);

  links.forEach(link => {
    link.addEventListener("click", function (event) {
      const section = document.getElementById(
        link.getAttribute("href").slice(1)
      );
      if (!section) return;

      event.preventDefault();
      const reducedMotion = window.matchMedia(
        "(prefers-reduced-motion: reduce)"
      ).matches;

      section.scrollIntoView({
        behavior: reducedMotion ? "auto" : "smooth",
        block: "start"
      });

      history.replaceState(null, "", link.getAttribute("href"));
      setActive(section.id);
    });
  });

  updateActiveSection();
})();
</script>
