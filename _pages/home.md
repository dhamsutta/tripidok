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
  <button onclick="showQuote()" style="margin-top: 1rem;">สุ่มใหม่</button>
</section>

<script>
let quotes = [];

function showQuote() {
  if (quotes.length === 0) return;

  const random = Math.floor(Math.random() * quotes.length);
  const quote = quotes[random];
  const html = `"${quote.quote}"<br><br>— <i>${quote.source}</i>`;
  document.getElementById("buddha-quote").innerHTML = html;
}

document.addEventListener("DOMContentLoaded", function () {
  fetch("{{ '/assets/data/quotes.json' | relative_url }}")
    .then((response) => response.json())
    .then((data) => {
      quotes = data;
      showQuote(); // แสดงพุทธพจน์ตอนโหลดครั้งแรก
    })
    .catch((err) => {
      console.error("โหลดพุทธพจน์ล้มเหลว:", err);
      document.getElementById("buddha-quote").innerText = "ไม่สามารถโหลดพุทธพจน์ได้";
    });
});
</script>