---
title: ruby
layout: default-aligned
---

<h3 class="text-center">All Posts on Ruby</h3>
<div class="row row-cols-1 row-cols-md-3 g-4">
    {% for post in site.tags.ruby %}
    <div class="col">
          <div class="card border-0 h-100">
              <div class="card-body">
                  <small class="text-muted postDate">{{ post.date | date: "%d %B %Y" }}</small>
                  <h5 class="card-title"><a href="{{ site.url }}{{ post.url | relative_url }}" class="text-dark">{{post.title}}</a></h5>
                  <p class="card-text">{{ post.excerpt }}</p>
              </div>
          </div>
    </div>
    {% endfor %}
</div>