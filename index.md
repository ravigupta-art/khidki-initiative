---
layout: default
title: Home
---

<div class="jumbotron jumbotron-fluid">
  <div class="container">
    {% if site.data.index.title %}
    <h1 class="text-center text-title font-weight-bold">{{ site.data.index.title }}</h1>
    {% endif %}
    <p class="text-center lead">{{ site.data.index.para1 }}</p>
    <p class="text-center lead"><mark>{{ site.data.index.para2 }}</mark></p><br>
  </div>
  <div class="col-md-4 offset-md-4">
    <a href="/upcoming-talks.html" class="btn btn-primary btn-lg btn-block" role="button" aria-pressed="true">Upcoming Talks</a>
    <a href="/past-talks.html" class="btn btn-primary btn-lg btn-block" role="button" aria-pressed="true">Past Talks</a>
  </div>
</div>
