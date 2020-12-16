---
layout: page
title: People
permalink: /people/
---

We have some great people working at the Dean Lab - meet some of them below.

{% raw %}

<div class="container">
  <div class="row">
{% endraw %}

{% for person in site.people %}
{% if person.imageid %}
{% capture imageurl %}https://res.cloudinary.com/{{site.cloudinary_id}}/image/upload/b_rgb:4892d1,c_lpad,h_350,q_100,w_500/{{person.imageid}}{% endcapture %}
{% elsif person.imageurl %}
{% capture imageurl %}{{person.imageurl}}{% endcapture %}
{% else %}{% capture imageurl %}http://res.cloudinary.com/codegaucho/image/upload/c_scale,w_256/v1381379684/ecibwsnz20ljfshmscy5{% endcapture %}
{% endif %}

  <div class="col-sm-4">
    <div class="card">
      <img alt="100%x200" class="card-img-top img-responsive" style="display: block;" src="{{ imageurl }}">
      <div class="card-block">

        <h3 class="card-title"><a href="{{ person.permalink }}">{{ person.name }}</a></h3>
        <h4>{{ person.title }}</h4>
        <p class="card-text">{{ person.description }}</p>
        <p class="card-text"><small class="text-muted"><a href="{{ person.permalink }}">More...</a></small></p>
      </div><!-- card-block -->

  </div><!-- card -->
</div><!-- col-sm-4 -->
{% endfor %}

{% raw %}

  </div><!-- row -->
</div><!-- container -->
{% endraw %}
