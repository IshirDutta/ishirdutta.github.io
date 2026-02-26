---
layout: page
title: presentations
permalink: /presentations/
description: Selected oral and poster presentations.
nav: true
nav_order: 4

# Categorized by Presentation Type
talk_categories:
  - name: "talks"
    icon: "fa-solid fa-microphone-lines"
    talks:
      - title: "The Changing Role of Reactive Nitrogen in the Troposphere"
        event: PhD Thesis Defense
        location: "Cambridge, MA"
        year: "April 2025"
        youtube_id: QruNGJy1zhw
        links:
          - url: "https://dspace.mit.edu/handle/1721.1/159889"
            text: "Thesis Link"
        #   - url: "#"
        #     text: "Slides (PDF)"

      - title: "The Global Tropospheric Budget of NOy"
        event: AGU 2024
        location: "Washington, DC"
        year: "December 2024"
        youtube_id: 3f5dEdNm-NU
        desc: "A54E: Global Tropospheric Reactive Nitrogen: Sources, Chemistry, Fate, and Impacts II Oral"
        links:
        #   - url: "#"
        #     text: "Slides (PDF)"
          - url: "https://agu.confex.com/agu/agu24/meetingapp.cgi/Paper/1694407"
            text: "Abstract"
        
      - title: "Exploring Deposition Observations as a Constraint on Emissions in the United States"
        event: AGU 2021
        location: "New Orleans, LA"
        year: "December 2021"
        youtube_id: FtWjbA0FAo0
        desc: "A23D: General Session: Atmospheric Chemistry and Composition III Oral"
        links:
        #   - url: "#"
        #     text: "Slides (PDF)"
          - url: "https://agu.confex.com/agu/fm21/meetingapp.cgi/Paper/829403"
            text: "Abstract"

  - name: "posters"
    icon: "fa-solid fa-chalkboard-user"
    talks:
      - title: "Characterizing the Global Tropospheric Budget of NOy"
        event: "10th International GEOS-Chem Meeting (IGC 11)"
        location: "St. Louis, MO"
        year: "June 2024"
        # desc: "Presented findings on global oxidized nitrogen budgets using the GEOS-Chem model."

      - title: "Characterizing the Global Tropospheric Budget of NOy"
        event: "AGU Annual Meeting 2023"
        location: "San Francisco, CA"
        year: "Dec 2023"
        # desc: "Session: Atmospheric Chemistry and Composition."

      - title: "Naturally occurring nanoparticles in water resource recovery facilities"
        event: "Association of Environmental Engineering and Science Professors (AEESP)"
        location: "Ann Arbor, MI"
        year: "June 2017"
        desc: "Collaboration with J. Smeraldi, L. Y. Tseng, and D. Rosso."

      - title: "Biogenic nanoparticles in wastewater treatment"
        event: "Undergraduate Research Day, Syracuse University"
        location: "Syracuse, NY"
        year: "Nov 2016"
        # desc: "Undergraduate research conducted in the Tseng Lab."

      - title: "Möbius polarization of light"
        event: "Frontiers in Optics/Laser Science, The Optical Society"
        location: "Rochester, NY"
        year: "Oct 2016"
        # desc: "Research on paraxial light beams and polarization topology."

---

<div class="talks">
{% for category in page.talk_categories %}
  <div class="category-section mt-5">
    <h2 class="category-title border-bottom pb-2">
      <i class="{{ category.icon }}"></i> {{ category.name }}
    </h2>
    
    {% for talk in category.talks %}
    <div class="row mt-4">
      <div class="col-sm-2">
        <h5 class="badge font-weight-bold text-uppercase w-100" style="background-color: var(--global-theme-color) !important;">
            {{ talk.year }}
        </h5>
      </div>

      <div class="col-sm-10">
        <h5 class="title font-weight-bold mb-1">{{ talk.title }}</h5>
        <h6 class="font-italic" style="color: var(--global-theme-color);">
          {{ talk.event }} {% if talk.location %}| {{ talk.location }}{% endif %}
        </h6>
        
        <p class="mt-2" style="font-size: 0.95rem;">{{ talk.desc }}</p>

        {% if talk.youtube_id %}
        <div class="video-container my-3">
          <div class="video-wrapper-small">
            <div class="embed-responsive embed-responsive-16by9" style="border-radius: 8px; overflow: hidden;">
              <iframe 
                class="embed-responsive-item" 
                src="https://www.youtube-nocookie.com/embed/{{ talk.youtube_id }}" 
                title="YouTube video player"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
                allowfullscreen>
              </iframe>
            </div>
          </div>
        </div>
        {% endif %}
        
        {% if talk.links %}
          <div class="links mt-2">
          {% for link in talk.links %}
            <a href="{{ link.url }}" class="btn btn-sm custom-talk-btn"
            target="_blank" rel="noopener">
              {% if link.text contains 'Poster' or link.text contains 'Slides' %}
                <i class="fa-solid fa-file-pdf"></i>
              {% else %}
                <i class="fa-solid fa-link"></i>
              {% endif %}
              {{ link.text }}
            </a>
          {% endfor %}
          </div>
        {% endif %}
      </div>
    </div>
    {% if forloop.last == false %}<hr class="light-hr">{% endif %}
    {% endfor %}
  </div>
{% endfor %}
</div>