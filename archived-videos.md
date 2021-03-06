---
layout: normal
title: Archived Talks
---
<div class="jumbotron jumbotron-fluid">
  <div class="container">
    <h1 class="text-center text-banner font-weight-bold text-title">Archived Videos</h1><!-- Card padding is custom css added to have a proper space between h1 and cards -->
    <br>

    {% assign no_of_videos = site.data.archived-videos | size %}
      {% assign count = 0 %}
      {% assign half = no_of_videos | divided_by: 2 %}
      {% for item in (1..half) %}
        {% if site.data.archived-videos.first %}
           <div class="card-deck mb-3 text-center card-padding">
             {% for j in (1..2) %}
              <div class="card mb-4 box-shadow">
                <div class="card-header">
                  <h4 class="my-0 font-weight-normal text-title"><strong>{{ site.data.archived-videos[count].videotitle }}</strong></h4>
                </div>
                <div class="card-body">
                  <div class="embed-responsive embed-responsive-16by9">
                   {% if site.data.archived-videos[count].videotype == 'youtube' %}
                     <iframe src="https://www.youtube.com/embed/{{ site.data.archived-videos[count].videoID }}" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                     {% elsif site.data.archived-videos[count].videotype == 'vimeo' %}
                     <iframe src="https://player.vimeo.com/video/{{ site.data.archived-videos[count].videoID }}" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                   {% endif %}
                  </div>
                  <h5><br>{{site.data.archived-videos[count].videodescription }}</h5><br>
                  {% if site.data.archived-videos[count].resource-type %}
                  <p><span class="font-weight-bold">Resource type:</span> {{ site.data.archived-videos[count].resource-type }}</p>
                  {% endif %}
                  {% if site.data.archived-videos[count].app-tested %}
                  <p><span class="font-weight-bold">Application tested with:</span> {{ site.data.archived-videos[count].app-tested }}</p>
                  {% endif %}
                  {% if site.data.archived-videos[count].download-links %}
                  <ul class="list-unstyled mt-3 mb-4">
                    <li class="font-weight-bold">download-links:</li>
                    {% for entry in site.data.archived-videos[count].download-links %}
                     <li class="download-links">{{ entry.link }}
                     </li><br>
                    {% endfor %}
                  </ul>
                  {% endif %}
                </div>
              </div>
              {% assign count = count | plus:1 %}
             {% endfor %}
           </div>

        {% endif %}
      {% endfor %}
      {% assign odd_videos = no_of_videos | modulo: 2 %}
      {% if odd_videos != 0 %}
        <div class="card-deck mb-3 text-center">
          <div class="card mb-4 box-shadow">
            <div class="card-header">
              <h4 class="my-0 font-weight-normal text-title"><strong>{{ site.data.archived-videos[count].videotitle }}</strong></h4>
            </div>
            <div class="card-body">
              <div class="embed-responsive embed-responsive-16by9">
               {% if site.data.archived-videos[count].videotype == 'youtube' %}
                 <iframe src="https://www.youtube.com/embed/{{ site.data.archived-videos[count].videoID }}" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                 {% elsif site.data.archived-videos[count].videotype == 'vimeo' %}
                 <iframe src="https://player.vimeo.com/video/{{ site.data.archived-videos[count].videoID }}" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
               {% endif %}
              </div>
              <h5><br>{{site.data.archived-videos[count].videodescription }}</h5><br>
              {% if site.data.archived-videos[count].resource-type %}
              <p><span class="font-weight-bold">Resource type:</span> {{ site.data.archived-videos[count].resource-type }}</p>
              {% endif %}
              {% if site.data.archived-videos[count].app-tested %}
              <p><span class="font-weight-bold">Application tested with:</span> {{ site.data.archived-videos[count].app-tested }}</p>
              {% endif %}
              {% if site.data.archived-videos[count].download-links %}
              <ul class="list-unstyled mt-3 mb-4">
                <li class="font-weight-bold">download-links:</li>
                {% for entry in site.data.archived-videos[count].download-links %}
                 <li class="download-links">{{ entry.link }}
                 </li><br>
                {% endfor %}
              </ul>
              {% endif %}
            </div>
          </div>
        </div>
      {% endif %}


  </div>
</div>
