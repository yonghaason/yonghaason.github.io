---
layout: page
permalink: /publications/
title: publications
description: Author order follows the paper (often alphabetical in cryptography venues).
nav: true
nav_order: 2
---

<ul class="nav nav-tabs pub-tabs" role="tablist">
  <li class="nav-item">
    <a class="nav-link active" id="tab-international" href="#international" data-target="international" role="tab" aria-controls="international" aria-selected="true">International</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="tab-domestic" href="#domestic" data-target="domestic" role="tab" aria-controls="domestic" aria-selected="false">Domestic</a>
  </li>
</ul>

<div class="tab-content pub-tab-content">
  <div class="tab-pane fade show active" id="international" role="tabpanel" aria-labelledby="tab-international">
    <div class="publications">
      {% bibliography --query @*[category=international] %}
    </div>
  </div>
  <div class="tab-pane fade" id="domestic" role="tabpanel" aria-labelledby="tab-domestic">
    <div class="publications">
      {% bibliography --query @*[category=domestic] %}
      <p class="pub-empty">No domestic publications listed yet.</p>
    </div>
  </div>
</div>

<script>
  // Lightweight tab switching (no jQuery/Bootstrap JS dependency)
  document.querySelectorAll('.pub-tabs .nav-link').forEach(function (tab) {
    tab.addEventListener('click', function (e) {
      e.preventDefault();
      document.querySelectorAll('.pub-tabs .nav-link').forEach(function (t) {
        t.classList.remove('active');
        t.setAttribute('aria-selected', 'false');
      });
      document.querySelectorAll('.pub-tab-content .tab-pane').forEach(function (pane) {
        pane.classList.remove('active', 'show');
      });
      tab.classList.add('active');
      tab.setAttribute('aria-selected', 'true');
      var pane = document.getElementById(tab.dataset.target);
      pane.classList.add('active', 'show');
      history.replaceState(null, '', '#' + tab.dataset.target);
    });
  });
  // Open the tab named in the URL hash, e.g. /publications/#domestic
  if (location.hash) {
    var initial = document.querySelector('.pub-tabs .nav-link[data-target="' + location.hash.slice(1) + '"]');
    if (initial) initial.click();
  }
</script>
