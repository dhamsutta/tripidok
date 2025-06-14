---
layout: page
title: ค้นหา
permalink: /search/
---

<input type="text" id="search-input" placeholder="ค้นหา..." style="width:100%; padding: 0.5rem; margin-bottom: 1rem;" />

<ul id="results-container"></ul>

<script src="https://unpkg.com/simple-jekyll-search/dest/simple-jekyll-search.min.js"></script>
<script>
  SimpleJekyllSearch({
    searchInput: document.getElementById('search-input'),
    resultsContainer: document.getElementById('results-container'),
    json: '/search.json',
    searchResultTemplate: '<li><a href="{url}">{title}</a></li>',
    noResultsText: 'ไม่พบผลลัพธ์',
    limit: 10,
    fuzzy: false
  })
</script>