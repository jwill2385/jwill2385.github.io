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


You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
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
