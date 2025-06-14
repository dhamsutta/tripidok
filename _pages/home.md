---
layout: home
title: ธรรมสุตตะ
permalink: /
entries_heading: "โพสต์ล่าสุด"
header:
  overlay_image: /assets/images/hero.jpg
  overlay_filter: 0.3
  overlay_color: "#000"
---

{% include masthead.html %}

<div class="page__hero" style="position: relative;">
  {% if page.header.overlay_image %}
  <div class="page__hero--overlay" style="background-image: url('{{ page.header.overlay_image | relative_url }}');">
    <div class="wrapper">
      {% if page.title %}
      <h1 class="page__title" style="color: white;">{{ page.title }}</h1>
      {% endif %}
      {% if page.excerpt %}
      <p class="page__excerpt" style="color: white;">{{ page.excerpt }}</p>
      {% endif %}
    </div>
  </div>
  {% endif %}
</div>

<div class="wrapper" style="margin-top: 2rem;">
  <!-- Random Buddha Quote -->
  <div id="buddha-quote" style="padding: 1rem; color: #1B5E20; font-weight: bold; text-align: center;"></div>

  <script>
    fetch("/assets/data/quotes.json")
      .then(response => response.json())
      .then(data => {
        function showQuote() {
          const random = data[Math.floor(Math.random() * data.length)];
          document.getElementById("buddha-quote").innerHTML =
            `“${random.quote}”<br><small>${random.source}</small>`;
        }
        showQuote();
        setInterval(showQuote, 10000);
      });
  </script>

  <!-- Latest Posts -->
  <h2 class="archive__subtitle">{{ page.entries_heading | default: "โพสต์ล่าสุด" }}</h2>
  <ul class="list__posts">
    {% for post in site.posts limit:5 %}
    <li>
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <p>{{ post.excerpt | strip_html | truncate: 120 }}</p>
    </li>
    {% endfor %}
  </ul>
</div>