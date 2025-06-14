---
layout: home
title: "ธรรมสุตตะ"
excerpt: "ศึกษาพระธรรมตามพระไตรปิฎก"
header:
  overlay_color: "#000"
  overlay_filter: "0.3"
  overlay_image: /assets/images/hero.jpg
---
<!-- ✅ ตำแหน่งแสดงพุทธพจน์ -->
<div id="buddha-quote" style="text-align: center; font-style: italic; font-size: 1.1em; padding: 1em; color: #2e7d32;"></div>

<!-- ✅ ข้อความพุทธพจน์ในรูปแบบ JSON -->
<script id="buddha-quotes" type="application/json">
[
  "จงมีสติอยู่ทุกเมื่อ อย่าประมาทแม้เพียงลมหายใจเข้าออก",
  "ทางแห่งธรรมย่อมประเสริฐกว่าทางแห่งโลก",
  "เราจักระลึกถึงธรรมอันเป็นเครื่องตื่น",
  "ความโกรธเหมือนไฟ จงอย่าเป็นผู้เผาตนเอง",
  "ปัญญาเกิดจากการฟัง ผู้ฟังย่อมเจริญด้วยปัญญา"
]
</script>

<!-- ✅ JavaScript แรนด้อมใหม่ทุก 10 วินาที -->
<script>
  const quotes = JSON.parse(document.getElementById('buddha-quotes').textContent);
  const quoteBox = document.getElementById('buddha-quote');

  function showRandomQuote() {
    const random = quotes[Math.floor(Math.random() * quotes.length)];
    quoteBox.innerText = random;
  }

  showRandomQuote(); // แสดงทันทีตอนโหลด
  setInterval(showRandomQuote, 10000); // แรนด้อมใหม่ทุก 10 วิ
</script>