---
layout: page
title: teaching
permalink: /teaching/
description: Courses and outreach programs at Colgate University.
nav: true
nav_order: 5

# Grouping by Department/Category
teaching_categories:
  - name: "Outreach"
    dept_url: "https://www.colgate.edu/community/science-outreach"
    courses:
      - title: "Science Outreach Coordinator"
        year: "2013 — 2017"
        role: "Ho Tung Visualization Lab"
        desc: "Designed and implemented science demonstrations for local K-12 schools to foster interest in STEM."

  - name: "Physics & Astronomy"
    dept_url: "https://www.colgate.edu/academics/departments-programs/department-physics-and-astronomy"
    courses:
      - title: "PHYS 232: Introduction to Mechanics"
        year: "Spring 2015 — 2017"
        role: "Teaching Assistant"
        desc: "Led biweekly review sessions and graded problem sets for first-year physics majors focusing on classical mechanics."
      - title: "PHYS 131: Atoms and Waves"
        year: "Fall 2014 — 2016"
        role: "Teaching Assistant"
        desc: "Led biweekly review sessions and graded problem sets for first-year physics majors covering mechanics, electricity, and special relativity, and quantum mechanics."

  - name: "Mathematics"
    dept_url: "https://www.colgate.edu/academics/departments-programs/department-mathematics"
    courses:
      - title: "MATH 250: Number Theory and Mathematical Reasoning"
        year: "Spring 2016"
        role: "Teaching Assistant"
        desc: "Provided guidance on proof-writing techniques and abstract mathematical logic during office hours."
      - title: "MATH 214: Linear Algebra"
        year: "Fall 2015"
        role: "Teaching Assistant"
        desc: "Graded weekly assignments and held review sessions covering vector spaces and linear transformations."

  - name: "Core Curriculum & Interdisciplinary"
    dept_url: "https://www.colgate.edu/academics/core-curriculum"
    courses:
      - title: "FSEM 144: Emerging Global Challenges"
        year: "Fall 2015"
        role: "edX Online Course Developer"
        desc: "Developed digital content and interactive modules for the university's global outreach initiative."
        links:
          - url: "https://www.huffpost.com/entry/breaking-online-education_b_8526952"
            text: "Media Coverage"
      - title: "CORE 138S: Advent of the Atomic Bomb"
        year: "Spring 2015"
        role: "edX Online Course Developer"
        desc: "Curated archival materials and designed assessments for a massive open online course (MOOC)."
        links:
          - url: "https://er.educause.edu/articles/2015/11/engaging-alumni-and-students-using-online-education-technology"
            text: "Peer-reviewed Article"
      - title: "GEOG 328: Sustainability and Natural Resources"
        year: "Spring 2017"
        role: "Peer Tutor"
        desc: "Facilitated small-group study sessions focused on resource management and environmental policy."

---

<div class="teaching">
{% for category in page.teaching_categories %}
  <div class="category-section mt-5">
    <h2 class="category-title border-bottom pb-2">
      {% if category.dept_url %}
        <a href="{{ category.dept_url }}" target="_blank" style="color: inherit;">{{ category.name }}</a>
      {% else %}
        {{ category.name }}
      {% endif %}
    </h2>
    
    {% for course in category.courses %}
    <div class="row mt-4">
      <div class="col-sm-3">
        <h5 class="badge font-weight-bold primary-color-dark text-uppercase w-100">
          {{ course.year }}
        </h5>
      </div>
      <div class="col-sm-9">
        <h5 class="title font-weight-bold mb-1">{{ course.title }}</h5>
        <h6 class="font-italic text-primary">{{ course.role }}</h6>
        <p class="mt-2" style="font-size: 0.95rem;">{{ course.desc }}</p>
        
        {% if course.links %}
          <div class="links mt-2">
          {% for link in course.links %}
            <a href="{{ link.url }}" class="btn btn-outline-dark btn-sm p-1 px-2" target="_blank" rel="noopener">> {{ link.text }}</a>
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
