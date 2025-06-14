---
layout: home
title: "ธรรมสุตตะ"
permalink: /
excerpt: "ศึกษาพระธรรมตามพระไตรปิฎก"
entries_heading: "โพสต์ล่าสุด"
header:
  overlay_color: "#000"
  overlay_filter: "0.3"
  overlay_image: /assets/images/hero.jpg
---

> <div id="buddha-quote" style="padding: 1rem; color: #1B5E20; font-weight: bold; text-align: center;"></div>

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
