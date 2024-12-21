---
layout: page
title: Picza
description: Robotic dolly for conetent creators
img: assets/img/picza_full.jpg
importance: 2
category: work
giscus_comments: true
---

Product Design and Development - MIT 2.739

<div class="row justify-content-center">
    <div class="col-sm-12 mt-3 mt-md-0">
        <!-- YouTube video embed -->
        <iframe width="560" height="315" 
                src="https://www.youtube.com/embed/8OlQn_vJShk" 
                title="Picza Demo" 
                frameborder="0" 
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                allowfullscreen>
        </iframe>
    </div>
</div>

The Picza is a robotic dolly that provides amateur filmmakers the ability to shoot professional-level tracking, trucking, and arc shots.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/picza_full.jpg" title="Picza" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/picza_base.jpg" title="Base" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Design question: How can we enable amateur filmmakers to achieve these shots without relying on a cameraman and expensive equipment?

We narrowed in on our beachhead market of Micro-creators on Youtube with 1,000 to 250,000 followers
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/target_market_picza.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

And our Secondary market of Professional Video Equipment Rental Facilities
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/secondary_market_picza.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
Through our research we identifiyed that the majority of amateur creators lack access to a professional camera crew and typically rely on a stationary tripod to record all of their content. This restriction limits many cretors to develop content within the confine view of a fixed camera angle.


<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/picza_initial_concept.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-3 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/picza_woodenbase.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
        <div class="col-sm-3 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/picza_adjustable_strap.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left are initial concept sketches of our design. In the center we developed an initial prototype with a press fit to attach the tripod. On the right is an updated prototype using an adjustable velcro strap to hold in the tripod legs
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
