---
layout: default-aligned
---
<div class="search">
    <div class="form-group mb-3">
        <form action="/search.html" method="get">
        <input class="form-control" type="text" id="search-box" name="query" placeholder="Type your search and press Enter">
        </form>
    </div>
</div>

<ul id="search-results"></ul>

<!-- Script to show search result -->
<script>
window.store = {
  {% assign searchable_pages = site.pages | where_exp: "page", "page.menu == 'main'" %}
  {% assign searchable_documents = site.documents %}
  {% for page in searchable_pages %}
    {% assign searchable_documents = searchable_documents | push: page %}
  {% endfor %}
  {% for doc in searchable_documents %}
    "{{ doc.url | slugify }}": {
      "title": "{{ doc.title | xml_escape }}",
      "author": "{{ doc.author | xml_escape }}",
      "category": "{{ doc.category | xml_escape }}",
      "content": {{ doc.content | strip_html | jsonify }},
      "url": "{{ doc.url | xml_escape }}"
    }
    {% unless forloop.last %},{% endunless %}
  {% endfor %}
}
</script>

<!-- Custom JS -->
<script type="text/javascript" src="{{ 'assets/js/custom/lunr.js' | relative_url}}"></script>
<script type="text/javascript" src="{{ 'assets/js/custom/search.process.js' | relative_url}}"></script>