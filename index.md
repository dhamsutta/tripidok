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
<div id="buddha-quote" style="text-align: center; font-style: italic; font-size: 1.1em; padding: 1em; color: #2e7d32; transition: opacity 1s;"></div>
<div id="buddha-source" style="text-align: center; font-size: 0.9em; color: #444; transition: opacity 1s;"></div>

<script id="buddha-quotes" type="application/json">
[
  { "text": "จงมีสติอยู่ทุกเมื่อ อย่าประมาทแม้เพียงลมหายใจเข้าออก", "source": "ธัมมปทะ" },
  { "text": "ทางแห่งธรรมย่อมประเสริฐกว่าทางแห่งโลก", "source": "ขุททกนิกาย" },
  { "text": "เราจักระลึกถึงธรรมอันเป็นเครื่องตื่น", "source": "สังยุตตนิกาย" },
  { "text": "ความโกรธเหมือนไฟ จงอย่าเป็นผู้เผาตนเอง", "source": "องฺคุตฺตรนิกาย" }
]
</script>

<script>
  const quotes = JSON.parse(document.getElementById('buddha-quotes').textContent);
  const quoteBox = document.getElementById('buddha-quote');
  const sourceBox = document.getElementById('buddha-source');

  function showRandomQuote() {
    const random = quotes[Math.floor(Math.random() * quotes.length)];
    quoteBox.style.opacity = 0;
    sourceBox.style.opacity = 0;

    setTimeout(() => {
      quoteBox.innerText = `"${random.text}"`;
      sourceBox.innerText = `— ${random.source}`;
      quoteBox.style.opacity = 1;
      sourceBox.style.opacity = 1;
    }, 1000);
  }

  showRandomQuote();
  setInterval(showRandomQuote, 10000);
</script>