---
layout: default
title: home
---

<!-- Main Picture -->
<div class="container pt-3 d-lg-none">
    <div class="row text-center">
        <div class="col-lg-3">

        </div>
        <div class="col-lg-9">
            <img src="{{ 'assets/img/Qnods Main Page.png' | relative_url}}" class="img-fluid" alt="responsive image" width="960">
        </div>
    </div>
</div>

<!-- Content Start -->
<div class="container pt-3">
    <div class="row">

        <div class="col-lg-3">
            <div class="row">
                <form action="{{ '/search.html' | relative_url }}" method="get">
                    <input class="form-control" type="text" id="search-box" name="query" placeholder="looking for something ?">
                </form>
            </div>
            <div class="row py-5">
                <h5>About</h5>
                <p>
                    Hello, I am <a href="https://edwardjoesoef.com">Edward</a> and this is <b>Qnods</b>, a data science, fintech, and web related blog that I write as I learn new things in those fields. 
                    I also plan to put some notes that I write as I am doing certain coding works for my own reminder in this blog as well.
                    Other than that, I will also post some projects in this blog as well. 
                </p>
                <p style="word-spacing: 30px;">
                <a href="mailto:hello@qnods.com"><img src="{{ 'assets/img/envelope.svg' | relative_url}}" class="img-fluid" height=25 width=25></a>
                </p>
            </div>
        </div>
        <div class="col-lg-9">
            <h3>Latest Post</h3>
            <div class="row row-cols-1 row-cols-md-3 g-4">
              {% for post in site.posts limit:12 %}
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
        </div>

    </div>
</div>

<!-- Custom JS -->
<script type="text/javascript" src="{{ 'assets/js/custom/edward.custom.blog.js' | relative_url}}"></script>

