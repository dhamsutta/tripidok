---
layout: default
title: "ธรรมสุตตะ"
permalink: /
excerpt: "ศึกษาพระธรรมตามพระไตรปิฎก"
header:
  overlay_image: /assets/images/hero.jpg
  overlay_filter: "0.3"
  overlay_color: "#000"
---

<div id="buddha-quote" style="padding: 1rem; color: #1B5E20; font-weight: bold; text-align: center;"></div>

<script>
fetch("/assets/data/quotes.json")
  .then(response => response.json())
  .then(data => {
    const random = Math.floor(Math.random() * data.length);
    const quote = data[random];
    const html = `"${quote.quote}"<br><br>— <i>${quote.source}</i>`;
    document.getElementById("buddha-quote").innerHTML = html;
  });
</script>