---
layout: default
title: "ธรรมสุตตะ"
permalink: /
---

<header class="hero-header" style="background-image: url('/assets/images/hero.jpg'); background-size: cover; padding: 4rem 1rem; text-align: center; color: white;">
  <h1 style="font-size: 2.5rem; font-weight: bold; text-shadow: 1px 1px 2px black;">ธรรมสุตตะ</h1>
  <p style="font-size: 1.2rem; text-shadow: 1px 1px 2px black;">ศึกษาพระธรรมตามพระไตรปิฎก</p>
</header>

<section style="text-align: center; padding: 2rem;">
  <div id="buddha-quote" style="color: #1B5E20; font-weight: bold;"></div>
</section>

<script>
fetch("/assets/data/quotes.json")
  .then(res => res.json())
  .then(data => {
    const quote = data[Math.floor(Math.random() * data.length)];
    document.getElementById("buddha-quote").innerHTML = `"${quote.quote}"<br><br>— <i>${quote.source}</i>`;
  });
</script>