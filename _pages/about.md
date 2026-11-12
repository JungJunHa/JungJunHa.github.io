---
layout: about
title: about
permalink: /

profile:
  align: right
  image: profile.jpeg
  image_circular: false # crops the image to make it circular
  more_info: >
    <p class="profile-affil" style="font-family: var(--global-font-family, inherit); font-size: 0.85rem; font-weight: 600; margin-top: 0.5rem;">Korea University &nbsp;&middot;&nbsp; <a href="https://dmis.korea.ac.kr/" target="_blank" rel="noopener noreferrer">DMIS Lab</a></p>

research_interests:
  - title: Multimodal Reasoning
    description: How can we improve multimodal reasoning through better learning and reasoning processes?
    links:
      - name: MRPO
        url: https://aclanthology.org/2026.emnlp-main.1950/
  - title: Visual Representation & Grounding
    description: How can models preserve and utilize visual evidence for grounded reasoning?
    links:
      - name: SaMer
        url: https://arxiv.org/abs/2607.04605
      - name: CVRR
        url: https://arxiv.org/abs/2609.06746
  - title: Medical MLLMs
    description: How can we improve the reliability of medical MLLMs through better reasoning and data?
    links:
      - name: MRPO
        url: https://aclanthology.org/2026.emnlp-main.1950/
      - name: MedQual (Coming Soon) # no url yet -> shown as plain text

selected_papers: false # publications (selected / preprint) are rendered in the page body below
social: false # social icons are shown under the profile picture instead (see profile.more_info)

announcements:
  enabled: false # unused: the "news" section below lists the 3 latest posts from the news (/blog/) page
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

Hello! I am an M.S. student in Computer Science at [Korea University](https://info.korea.edu/en_info/under/computer_intro.do), advised by [Prof. Jaewoo Kang](https://scholar.google.com/citations?user=RaBZafQAAAAJ) at the [DMIS Lab](https://dmis.korea.ac.kr/). Previously, I worked as a research assistant at Yonsei University and as an AI Consultant at Deloitte Consulting.

My primary research interest lies in **Multimodal Reasoning**, focusing on **Reinforcement Learning**, **Visual Representation Learning**, and **Visual Grounding**. My research spans **Medical MLLMs** and general-purpose multimodal models, with particular attention to improving reasoning and the use of visual information.

I am interested in developing multimodal models that can reason reliably across diverse visual tasks. Building on my research in medical visual question answering, I aim to explore broader challenges in multimodal reasoning, particularly how models learn to reason and how visual information is represented and utilized.

<style>
  .profile-links {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 0.75rem 1.5rem;
    margin-top: 1.75rem;
    font-size: 0.9rem;
    font-weight: 700;
  }
  .profile-links a {
    color: var(--global-theme-color);
    text-decoration: none;
  }
  .profile-links a:hover {
    text-decoration: underline;
  }
  .profile-links a.cv-button {
    padding: 0.6rem 1rem;
    border-radius: 0.15rem;
    background-color: var(--global-theme-color);
    color: var(--global-bg-color);
  }
  .profile-links a.cv-button:hover {
    text-decoration: none;
    opacity: 0.9;
  }
  .profile-links i {
    margin-left: 0.3rem;
    font-size: 0.75em;
  }
</style>

<div class="profile-links">
  <a class="cv-button" href="{{ '/assets/pdf/Junha_Jung_CV.pdf' | relative_url }}" target="_blank" rel="noopener noreferrer">Curriculum vitae<i class="fa-solid fa-arrow-up-right"></i></a>
  <a href="https://scholar.google.com/citations?user=ieNiHkUAAAAJ" target="_blank" rel="noopener noreferrer">Scholar<i class="fa-solid fa-arrow-up-right"></i></a>
  <a href="https://github.com/JungJunHa" target="_blank" rel="noopener noreferrer">GitHub<i class="fa-solid fa-arrow-up-right"></i></a>
  <a href="https://www.linkedin.com/in/junha-jung-345961146/" target="_blank" rel="noopener noreferrer">LinkedIn<i class="fa-solid fa-arrow-up-right"></i></a>
  <a href="mailto:goodjungjun@korea.ac.kr">Email<i class="fa-solid fa-arrow-up-right"></i></a>
</div>

<div style="clear: both;"></div>

<div class="section-heading" style="margin-top: 3.5rem; padding-bottom: 0.4rem; border-bottom: 1px solid var(--global-divider-color); margin-bottom: 1rem;">
  <h2 class="mb-0" style="font-weight: 700;">
    News
  </h2>
</div>

<div class="news">
  <table class="table table-sm table-borderless">
    {% for post in site.posts limit: 3 %}
      <tr>
        <th scope="row" style="width: 20%">{{ post.date | date: '%b %Y' }}</th>
        <td>{{ post.title }}</td>
      </tr>
    {% else %}
      <tr><td>No news so far...</td></tr>
    {% endfor %}
  </table>
  <div style="text-align: left; font-size: 0.85rem; font-weight: 700;">
    <a href="{{ '/blog/' | relative_url }}">Show all news<i class="fa-solid fa-arrow-right" style="margin-left: 0.35rem; font-size: 0.75em;"></i></a>
  </div>
</div>

{% include pub_styles.liquid %}

<div
  class="section-heading d-flex align-items-center flex-wrap"
  style="gap: 1.5rem; margin-top: 3.5rem; padding-bottom: 0.4rem; border-bottom: 1px solid var(--global-divider-color); margin-bottom: 1rem;"
>
  <h2 class="mb-0" style="font-weight: 700;">
    Publications
  </h2>
  <select
    id="pub-filter"
    aria-label="Filter publications"
    style="padding: 0.2rem 0.5rem; border: 1px solid var(--global-divider-color); border-radius: 0.3rem; background-color: var(--global-bg-color); color: var(--global-text-color);"
  >
    <option value="all" selected>all</option>
    <option value="selected">published</option>
    <option value="preprint">preprint</option>
  </select>
  <a href="{{ '/publications/' | relative_url }}" style="margin-left: auto; font-size: 0.85rem; font-weight: 700;">All publications<i class="fa-solid fa-arrow-right" style="margin-left: 0.35rem; font-size: 0.75em;"></i></a>
</div>

<div class="publications" data-pub-group="all">
  {% bibliography --group_by none --max 10 %}
</div>

<div class="publications" data-pub-group="selected" style="display: none;">
  {% bibliography --group_by none --max 10 --query @*[selected=true]* %}
</div>

<div class="publications" data-pub-group="preprint" style="display: none;">
  {% bibliography --group_by none --max 10 --query @*[preprint=true]* %}
</div>

<p class="equal-contrib-note">* Equal contribution.</p>

<script>
  document.getElementById("pub-filter").addEventListener("change", function () {
    var value = this.value;
    document.querySelectorAll("[data-pub-group]").forEach(function (el) {
      el.style.display = el.getAttribute("data-pub-group") === value ? "" : "none";
    });
  });
</script>

<style>
  .research-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
  }
  .research-item {
    padding: 0.5rem 1.75rem 0.5rem 1.75rem;
    border-left: 1px solid var(--global-divider-color);
  }
  .research-item:first-child {
    padding-left: 0;
    border-left: none;
  }
  .research-num {
    display: inline-block;
    font-family: monospace;
    font-size: 0.75rem;
    padding: 0.15rem 0.45rem;
    border: 1px solid var(--global-divider-color);
    border-radius: 0.2rem;
    color: var(--global-theme-color);
  }
  .research-item h3 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 1.25rem 0 0.75rem;
  }
  .research-item p {
    font-size: 0.9rem;
    color: var(--global-text-color-light);
  }
  .research-links {
    font-size: 0.85rem;
    font-weight: 600;
  }
  .research-pending {
    color: var(--global-text-color-light);
    font-weight: 500;
  }
  .research-links .sep {
    margin: 0 0.5rem;
    color: var(--global-divider-color);
  }
  @media (max-width: 767px) {
    .research-grid {
      grid-template-columns: 1fr;
    }
    .research-item,
    .research-item:first-child {
      padding: 1.25rem 0;
      border-left: none;
      border-top: 1px solid var(--global-divider-color);
    }
    .research-item:first-child {
      border-top: none;
      padding-top: 0.5rem;
    }
  }
</style>

<div class="section-heading" style="margin-top: 3.5rem; padding-bottom: 0.4rem; border-bottom: 1px solid var(--global-divider-color); margin-bottom: 1rem;">
  <h2 class="mb-0" style="font-weight: 700;">Research Interests</h2>
</div>

<div class="research-grid">
  {% for item in page.research_interests %}
    <div class="research-item">
      <span class="research-num">{{ forloop.index | prepend: '0' | slice: -2, 2 }}</span>
      <h3>{{ item.title }}</h3>
      <p>{{ item.description }}</p>
      {% if item.links %}
        <div class="research-links">
          {% for link in item.links %}
            {% if link.url %}
              {% assign is_external = link.url | slice: 0, 4 %}
              <a href="{{ link.url }}" {% if is_external == 'http' %}target="_blank" rel="noopener noreferrer"{% endif %}>
                {{- link.name -}}
                {% if is_external == 'http' %}&nbsp;<i class="fa-solid fa-arrow-up-right fa-xs"></i>{% endif %}
              </a>
            {% else %}
              <span class="research-pending">{{ link.name }}</span>
            {% endif %}
            {% unless forloop.last %}<span class="sep">/</span>{% endunless %}
          {% endfor %}
        </div>
      {% endif %}
    </div>
  {% endfor %}
</div>
