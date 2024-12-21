---
layout: page
title: Picza
description: Robotic dolly for conetent creators
img: assets/img/picza_full.jpeg
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
        {% include figure.liquid loading="eager" path="assets/img/picza_full.jpeg" title="Picza" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/picza_base.jpeg" title="Base" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Design question: How can we enable amateur filmmakers to achieve these shots without relying on a cameraman and expensive equipment?

We narrowed in on our beachhead market as Micro-creators on Youtube with 1,000 to 250,000 followers
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/target_market_picza.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

And our Secondary market as Professional Video Equipment Rental Facilities
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/secondary_market_picza.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
Through our research, we identifiyed that the majority of amateur creators lack access to a professional camera crew and typically rely on a stationary tripod to record all of their content. This restriction limits many cretors to develop content within the confine view of a fixed camera angle.


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

To make Picza an effective product, we focused on creating a platform that minimizes user input on the front end while relying on a robust backend architecture.

Our prototype uses an Arduino microcontroller to interface with two drive motors through a separate controller. A PID controller was designed and fine-tuned to execute specific motion profiles with precision. By implementing mathematical models for various geometric shapes, we enabled the prototype to perform a range of motion profiles. Additionally, we integrated Bluetooth-based communication with a smartphone, enabling both real-time remote control and the ability to assign preprogrammed motion profiles.

<div class="row justify-content-center">
    <div class="col-sm-8">
        {% include figure.liquid path="assets/img/picza_demo.gif" title="Animated concept of Picza" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


We purchased an off the shelf tripod dolly, dissasembled its components, and modernized the design by adding a microcontroller and motors which lead to our finalized protoype.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/off_shelf_tripod.jpg" title="tripod" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/reverse_engineer.gif" title="Base" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


<div class="row justify-content-center">
    <div class="col-sm-8">
        {% include figure.liquid path="assets/img/picza_team.jpg" title="Picza Team" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Finalized Picza Prototype   
</div>

