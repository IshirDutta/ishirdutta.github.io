---
layout: page
title: talks
permalink: /talks/
description: A collection of my recorded seminar talks and presentations.
nav: true
nav_order: 4

talks:
  - id: QruNGJy1zhw
    title: "PhD Thesis Defense - The changing role of reactive nitrogen in the troposphere"
    date: "2025-04-11"
    # slides: /assets/pdf/talk_1_slides.pdf  # Path to your PDF in the assets folder

  - id: 3f5dEdNm-NU
    title: "AGU 2024 | The Global Tropospheric Budget of NOy "
    date: "2024-12-13"
    description: "A54E: Global Tropospheric Reactive Nitrogen: Sources, Chemistry, Fate, and Impacts II Oral"
    # slides: /assets/pdf/talk_1_slides.pdf  # Path to your PDF in the assets folder

  - id: FtWjbA0FAo0
    title: "AGU 2021 | Exploring Deposition Observations as a Constraint on Emissions in the United States"
    date: "2021-12-14"
    description: "A23D: General Session: Atmospheric Chemistry and Composition III Oral"
    # slides: /assets/pdf/talk_1_slides.pdf  # Path to your PDF in the assets folder
---

<div class="talks">
{% for talk in page.talks %}
  <div class="talk-item mb-5">
    
    <div class="d-flex justify-content-between align-items-center mb-1">
      <h3 class="title font-weight-bold mb-0">{{ talk.title }}</h3>
      {% if talk.slides %}
        <a href="{{ talk.slides | relative_url }}" class="btn btn-outline-danger btn-sm" target="_blank">
          <i class="fas fa-file-pdf"></i> Slides
        </a>
      {% endif %}
    </div>

    <p class="post-meta text-muted mb-3" style="font-size: 0.9rem;">
      <i class="fas fa-calendar-alt"></i> {{ talk.date | date: "%B %d, %Y" }}
    </p>

    <div class="ratio ratio-16x9 mb-3 shadow-sm" style="border-radius: 8px; overflow: hidden;">
      <iframe 
        src="https://www.youtube-nocookie.com/embed/{{ talk.id }}?rel=0&amp;vq=hd1080&amp;modestbranding=1" 
        title="{{ talk.title }}" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
        allowfullscreen>
      </iframe>
    </div>
    
    {% if talk.description %}
    <p class="description px-1" style="font-size: 0.95rem; line-height: 1.5;">
      {{ talk.description }}
    </p>
    {% endif %}
    
    {% if forloop.last == false %}
      <hr class="mt-4 mb-5">
    {% endif %}
  </div>
{% endfor %}
</div>