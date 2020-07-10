---
layout: normal
title: Past Talks
---

<div class="jumbotron jumbotron-fluid">
  <div class="container">
    <h1 class="text-center text-banner font-weight-bold text-title">Past Talks</h1><!-- Card padding is custom css added to have a proper space between h1 and cards -->


    {% assign no_of_talks = site.data.past-talks | size %}
    {% assign counter = 0 %}
    {% for item in (1..no_of_talks) %}
      <div class="card bg-dark text-white mb-4">
        <div class="row no-gutters">
          <div class="col-md-8">
            <img src="/assets/images/talks/{{ site.data.past-talks[counter].talkPoster }}" class="card-img" alt="Poster for {{ site.data.past-talks[count].talk-title }} by {{ site.data.past-talks[counter].presenter }}" style="max-width: 800px;">
          </div>
          <div class="col-md-4">
            <div class="card-body">
              <h5 class="card-title"><strong>{{ site.data.past-talks[counter].talk-title }}</strong></h5>
              <p><span class="font-weight-bold">Presenter:</span> {{ site.data.past-talks[counter].presenter }}</p>
              <p><span class="font-weight-bold">Date:</span> {{ site.data.past-talks[counter].date }}</p>
              <p><span class="font-weight-bold">Time:</span> {{ site.data.past-talks[counter].time }}</p>
              <p><span class="font-weight-bold">Link:</span> {{ site.data.past-talks[counter].link }}</p>
            </div>
          </div>
        </div>
      </div>
    {% assign counter = counter | plus:1 %}
    {% endfor %}


  </div>
</div>
