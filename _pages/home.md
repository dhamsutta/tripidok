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

<section style="display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 1rem; padding: 2rem;">
  <a href="/categories/" class="card">หมวดหมู่</a>
  <a href="/tags/" class="card">แท็ก</a>
  <a href="/radio/" class="card">ธรรมบรรยาย</a>
  <a href="/glossary/" class="card">อภิธานศัพท์</a>
</section>

<style>
.card {
  display: block;
  padding: 1rem;
  background: #f2f2f2;
  border-radius: 8px;
  text-align: center;
  font-weight: bold;
  text-decoration: none;
  color: #1B5E20;
  box-shadow: 1px 1px 4px rgba(0,0,0,0.1);
}
.card:hover {
  background: #e0f2f1;
}
</style>

<script>
fetch("/assets/data/quotes.json")
  .then(res => res.json())
  .then(data => {
    const quote = data[Math.floor(Math.random() * data.length)];
    document.getElementById("buddha-quote").innerHTML = `"${quote.quote}"<br><br>— <i>${quote.source}</i>`;
  });
</script>