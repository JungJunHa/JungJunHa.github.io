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
      <a href="assets/pdf/example_pdf.pdf" title="CV" target="_blank" rel="noopener noreferrer"><i class="ai ai-cv"></i></a>
    </div>

selected_papers: false # publications (selected / preprint) are rendered in the page body below
social: false # social icons are shown under the profile picture instead (see profile.more_info)

announcements:
  enabled: false # news is rendered in the page body below (limit/scrollable still apply)
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

<h2>
  <a href="{{ '/news/' | relative_url }}" style="color: inherit">news</a>
</h2>

{% include news.liquid limit=true %}

<div class="d-flex align-items-center flex-wrap" style="gap: 0.75rem;">
  <h2 class="mb-0">
    <a href="{{ '/publications/' | relative_url }}" style="color: inherit">publications</a>
  </h2>
  <select
    id="pub-filter"
    aria-label="Filter publications"
    style="padding: 0.2rem 0.5rem; border: 1px solid var(--global-divider-color); border-radius: 0.3rem; background-color: var(--global-bg-color); color: var(--global-text-color);"
  >
    <option value="selected" selected>selected</option>
    <option value="preprint">preprint</option>
  </select>
</div>

<div class="publications" data-pub-group="selected">
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
