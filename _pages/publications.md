---
layout: page
permalink: /publications/
title: publications
title_ko: 논문
description: Author order follows the paper (often alphabetical in cryptography venues). "BK Top-tier" marks venues on the BK21 Computer Science top-tier conference list.
description_ko: 저자 순서는 논문에 실린 순서를 따릅니다 (암호학 분야는 알파벳 순인 경우가 많습니다). "BK Top-tier"는 BK21 컴퓨터과학 분야 우수 국제학술대회 목록에 포함된 학회를 뜻합니다.
nav: true
nav_order: 2
---

<ul class="nav nav-tabs pub-tabs" role="tablist">
  <li class="nav-item">
    <a class="nav-link active" id="tab-international" href="#international" data-target="international" role="tab" aria-controls="international" aria-selected="true"><span class="lang-en">International</span><span class="lang-ko">국제</span></a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="tab-domestic" href="#domestic" data-target="domestic" role="tab" aria-controls="domestic" aria-selected="false"><span class="lang-en">Domestic</span><span class="lang-ko">국내</span></a>
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
      <p class="pub-empty"><span class="lang-en">No domestic publications listed yet.</span><span class="lang-ko">아직 등록된 국내 논문이 없습니다.</span></p>
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
