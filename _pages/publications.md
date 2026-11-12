---
layout: page
permalink: /publications/
title: Publications
description: Papers on Multimodal Reasoning, Visual Representation & Grounding, Medical MLLMs by Junha Jung
nav: true
nav_order: 1
---

<!-- _pages/publications.md -->

{% include pub_styles.liquid %}

<style>
  /* sub-page heading: capitalised and larger */
  .post-header .post-title {
    font-size: 3.25rem;
    text-transform: capitalize;
  }
  .post-header .post-description {
    font-size: 1rem;
    color: var(--global-text-color-light);
  }
  .pub-filter-bar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 0.75rem;
    padding: 0.75rem 0;
    border-top: 1px solid var(--global-divider-color);
    border-bottom: 1px solid var(--global-divider-color);
  }
  .pub-filter-tabs {
    display: flex;
    gap: 0.25rem;
  }
  .pub-filter-tabs button {
    padding: 0.45rem 1rem;
    border: none;
    border-radius: 0.15rem;
    background: transparent;
    color: var(--global-text-color-light);
    font-size: 0.85rem;
    cursor: pointer;
  }
  .pub-filter-tabs button:hover {
    color: var(--global-text-color);
  }
  .pub-filter-tabs button.active {
    background-color: var(--global-theme-color);
    color: var(--global-bg-color);
  }
  .pub-filter-count {
    font-size: 0.8rem;
    color: var(--global-text-color-light);
  }
</style>

<div class="pub-filter-bar">
  <div class="pub-filter-tabs" role="tablist" aria-label="Filter publications">
    <button type="button" class="active" data-filter="all" role="tab" aria-selected="true">All</button>
    <button type="button" data-filter="selected" role="tab" aria-selected="false">Published</button>
    <button type="button" data-filter="preprint" role="tab" aria-selected="false">Preprints</button>
  </div>
  <span class="pub-filter-count" id="pub-filter-count"></span>
</div>

<div class="publications" data-pub-group="all">

{% bibliography %}

</div>

<div class="publications" data-pub-group="selected" style="display: none;">

{% bibliography --query @*[selected=true]* %}

</div>

<div class="publications" data-pub-group="preprint" style="display: none;">

{% bibliography --query @*[preprint=true]* %}

</div>

<p class="equal-contrib-note">* Equal contribution.</p>

<script>
  (function () {
    var buttons = document.querySelectorAll(".pub-filter-tabs button");
    var groups = document.querySelectorAll("[data-pub-group]");
    var count = document.getElementById("pub-filter-count");

    function show(filter) {
      groups.forEach(function (el) {
        var visible = el.getAttribute("data-pub-group") === filter;
        el.style.display = visible ? "" : "none";
        if (visible) {
          var n = el.querySelectorAll("ol.bibliography > li").length;
          count.textContent = n + (n === 1 ? " paper" : " papers");
        }
      });
      buttons.forEach(function (b) {
        var active = b.getAttribute("data-filter") === filter;
        b.classList.toggle("active", active);
        b.setAttribute("aria-selected", active ? "true" : "false");
      });
    }

    buttons.forEach(function (b) {
      b.addEventListener("click", function () {
        show(b.getAttribute("data-filter"));
      });
    });
    show("all");
  })();
</script>
