---
layout: about
title: about
permalink: /
subtitle: <a href='#'>Affiliations</a>. Address. Contacts. Motto. Etc.

profile:
  align: left
  image: profile.jpeg
  image_circular: false # crops the image to make it circular
  more_info: >
    <p>555 your office number</p>
    <p>123 your address street</p>
    <p>Your City, State 12345</p>
    <div class="profile-socials" style="display: flex; gap: 0.9rem; font-size: 1.4rem; margin-top: 0.6rem;">
      <a href="mailto:you@example.com" title="email"><i class="fa-solid fa-envelope"></i></a>
      <a href="https://www.linkedin.com/in/your-linkedin-id" title="LinkedIn" target="_blank" rel="noopener noreferrer"><i class="fa-brands fa-linkedin"></i></a>
      <a href="https://scholar.google.com/citations?user=qc6CJjYAAAAJ" title="Google Scholar" target="_blank" rel="noopener noreferrer"><i class="ai ai-google-scholar"></i></a>
      <a href="assets/pdf/Junha_Jung_CV.pdf" title="CV" target="_blank" rel="noopener noreferrer"><i class="ai ai-cv"></i></a>
    </div>

research_interests:
  - title: Interest one
    description: A one- or two-sentence question that describes this research direction.
    links:
      - name: Project A
        url: "#"
      - name: Project B
        url: "#"
  - title: Interest two
    description: A one- or two-sentence question that describes this research direction.
    links:
      - name: Project C
        url: https://example.com
  - title: Interest three
    description: A one- or two-sentence question that describes this research direction.
    links:
      - name: Project D
        url: https://example.com

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

Write your biography here. Tell the world about yourself. Link to your favorite [subreddit](https://www.reddit.com). You can put a picture in, too. The code is already in, just name your picture `prof_pic.jpg` and put it in the `img/` folder.

Put your address / P.O. box / other info right below your picture. You can also disable any of these elements by editing `profile` property of the YAML header of your `_pages/about.md`. Edit `_bibliography/papers.bib` and Jekyll will render your [publications page](/al-folio/publications/) automatically.

Link to your social media connections, too. This theme is set up to use [Font Awesome icons](https://fontawesome.com/) and [Academicons](https://jpswalsh.github.io/academicons/), like the ones below. Add your Facebook, Twitter, LinkedIn, Google Scholar, or just disable all of them.

<div style="clear: both;"></div>

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

<div class="section-heading" style="margin-top: 1.5rem; padding-bottom: 0.4rem; border-bottom: 1px solid var(--global-divider-color); margin-bottom: 1rem;">
  <h2 class="mb-0" style="font-weight: 700;">research interests</h2>
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
            {% assign is_external = link.url | slice: 0, 4 %}
            <a href="{{ link.url }}" {% if is_external == 'http' %}target="_blank" rel="noopener noreferrer"{% endif %}>
              {{- link.name -}}
              {% if is_external == 'http' %}&nbsp;<i class="fa-solid fa-arrow-up-right fa-xs"></i>{% endif %}
            </a>
            {% unless forloop.last %}<span class="sep">/</span>{% endunless %}
          {% endfor %}
        </div>
      {% endif %}
    </div>
  {% endfor %}
</div>

<div class="section-heading" style="margin-top: 3.5rem; padding-bottom: 0.4rem; border-bottom: 1px solid var(--global-divider-color); margin-bottom: 1rem;">
  <h2 class="mb-0" style="font-weight: 700;">
    <a href="{{ '/blog/' | relative_url }}" style="color: inherit">news</a>
  </h2>
</div>

<div class="news">
  <table class="table table-sm table-borderless">
    {% for post in site.posts limit: 3 %}
      <tr>
        <th scope="row" style="width: 20%">{{ post.date | date: '%b %Y' }}</th>
        <td>
          <a class="news-title" href="{{ '/blog/' | relative_url }}#{{ post.slug }}">{{ post.title }}</a>
        </td>
      </tr>
    {% else %}
      <tr><td>No news so far...</td></tr>
    {% endfor %}
  </table>
</div>

<div
  class="section-heading d-flex align-items-center flex-wrap"
  style="gap: 1.5rem; margin-top: 3.5rem; padding-bottom: 0.4rem; border-bottom: 1px solid var(--global-divider-color); margin-bottom: 1rem;"
>
  <h2 class="mb-0" style="font-weight: 700;">
    <a href="{{ '/publications/' | relative_url }}" style="color: inherit">publications</a>
  </h2>
  <select
    id="pub-filter"
    aria-label="Filter publications"
    style="padding: 0.2rem 0.5rem; border: 1px solid var(--global-divider-color); border-radius: 0.3rem; background-color: var(--global-bg-color); color: var(--global-text-color);"
  >
    <option value="all" selected>all</option>
    <option value="selected">selected</option>
    <option value="preprint">preprint</option>
  </select>
</div>

<div class="publications" data-pub-group="all">
  {% bibliography --group_by none %}
</div>

<div class="publications" data-pub-group="selected" style="display: none;">
  {% bibliography --group_by none --query @*[selected=true]* %}
</div>

<div class="publications" data-pub-group="preprint" style="display: none;">
  {% bibliography --group_by none --query @*[preprint=true]* %}
</div>

<script>
  document.getElementById("pub-filter").addEventListener("change", function () {
    var value = this.value;
    document.querySelectorAll("[data-pub-group]").forEach(function (el) {
      el.style.display = el.getAttribute("data-pub-group") === value ? "" : "none";
    });
  });
</script>
