---
layout: page
permalink: /people/
title: people
nav: true
nav_order: 1
---

## Advisor

<div class="row people-advisor">
  <div class="col-sm-3 mb-3">
    {% include figure.liquid loading="eager" path="assets/img/yongha.png" class="img-fluid rounded z-depth-1" alt="Yongha Son" %}
  </div>
  <div class="col-sm-9">
    <h4 class="mt-0">Yongha Son (손용하)</h4>
    <p class="mb-2">
      Assistant Professor<br>
      Department of Convergence Security Engineering, Sungshin Women's University<br>
      Room 829, Bldg. Crystal B<br>
      <i class="fa-solid fa-envelope"></i> yongha DOT son AT sungshin.ac.kr<br>
      <a href="{{ '/cv/' | relative_url }}"><i class="fa-solid fa-file-lines"></i> Curriculum Vitae</a> &middot;
      <a href="https://scholar.google.com/citations?user={{ site.scholar_userid }}" target="_blank" rel="noopener noreferrer"><i class="ai ai-google-scholar"></i> Google Scholar</a>
    </p>
    <p>
      Yongha Son is an Assistant Professor at Sungshin Women's University since March 2024.
      Before that, he was a Senior Researcher in the Security Algorithm Lab at
      <a href="https://www.samsungsds.com/" target="_blank" rel="noopener noreferrer">Samsung SDS</a> (2020&ndash;2024).
      He received his Ph.D. in Mathematical Sciences from Seoul National University in 2020 under the supervision of
      <a href="https://www.math.snu.ac.kr/~jhcheon/xe2/" target="_blank" rel="noopener noreferrer">Prof. Jung Hee Cheon</a>,
      and his B.Sc. in Mathematics Education from Seoul National University in 2014.
    </p>
    <p class="mb-0">
      <b>Research interests:</b> secure computation and its applications (homomorphic encryption, MPC, PSI),
      post-quantum cryptography, and lattice-based cryptanalysis.
    </p>
  </div>
</div>

---

## Students

{% comment %}
  One card per student. To add a photo, put it in assets/img/people/ and change the src.
  The `program` line is free text (e.g. "Ph.D. student", "Integrated Ph.D. student", "M.S. student").
{% endcomment %}

{% assign students = "Taehun Kang|Ph.D. student|placeholder.svg;Hyun Ji Kwag|Ph.D. student|placeholder.svg;Junhyuk Kwon|Integrated Ph.D. student|placeholder.svg" | split: ";" %}

<div class="row people-grid">
  {% for s in students %}
    {% assign f = s | split: "|" %}
    <div class="col-6 col-sm-4 col-md-3 mb-4 text-center">
      <img src="{{ f[2] | prepend: '/assets/img/people/' | relative_url }}" alt="{{ f[0] }}" class="img-fluid rounded z-depth-1 people-photo">
      <div class="people-name">{{ f[0] }}</div>
      <div class="people-program">{{ f[1] }}</div>
    </div>
  {% endfor %}
</div>
