---
title: notes
layout: default
---

<main class="container pt-3 pb-5">
    <h2 class="pb-3">All Posts from Python</h2>
    <div class="row row-cols-1 row-cols-md-3 g-4">
    {% for post in site.tags.python %}
      <div class="col">
        <div class="card h-100">
          <div class="card-body">
            <h4 class="card-title"><a href="{{ site.url }}{{ post.url | relative_url }}">{{post.title}}</a></h4>
            <p>
              {% if post.tags.size > 0 %}
                {{ post.tags | sort | join: " " }}
              {% endif %}
            </p>
            <p class="card-text">{{ post.excerpt }}</p>
          </div>
          <div class="card-footer">
            <small class="text-muted postDate">written on {{ post.date | date: "%d %B %Y" }}</small>
          </div>
        </div>
      </div>
    {% endfor %}
    </div>
</main>