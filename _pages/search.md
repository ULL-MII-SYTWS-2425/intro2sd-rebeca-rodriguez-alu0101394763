---
permalink: /search/
title: Search
---

{% capture initSearch %}

<form id="search-form" action="">
  <label class="label" for="search">Search term (accepts a regex):</label>
  <br/>
  <input class="input" id="search" type="text" name="search" 
        autofocus 
        placeholder="e.g. Promise" 
        autocomplete="off">
  
  <ul class="list  list--results" id="list">
  </ul>
</form>

<script type="text/javascript" src='ull-mii-sytws-2425.github.io/intro2sd-rebeca-rodriguez-alu0101394763/assets/src/fetch.js'></script>
<script type="text/javascript" src='ull-mii-sytws-2425.github.io/intro2sd-rebeca-rodriguez-alu0101394763/assets/src/search.js'></script>

<script type="text/javascript">

  const search = new JekyllSearch(
    '{{site.url}}/assets/src/search.json',
    '#search',
    '#list',
    '{{ site.baseurl }}' // put here your /baseurl/
  );
  search.init(); 
  
</script>

<noscript>Please enable JavaScript to use the search form.</noscript>

{% endcapture %}

{{ initSearch | lstrip }}