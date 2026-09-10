---
layout: page
title: Cookability
description: Cooking recipe app that suggest new dishes and what to make
img: assets/img/cookability/logo.jpg
importance: 4
category: fun
---

Cookability is a personal project that helps answer an everyday question: what should I cook tonight? The iOS and Android recipe app keeps recipes in one place and suggests new dishes based on what you enjoy, how much time you have, and the ingredients already in your kitchen.

## Full demo

<div class="row justify-content-center">
    <div class="col-sm-10">
        <video controls playsinline preload="metadata" aria-label="Cookability full app demo" class="img-fluid rounded z-depth-1" style="display: block; width: 100%; max-height: 75vh;">
            <source src="{{ '/assets/video/cookability/cookability-demo.mp4' | relative_url }}" type="video/mp4">
            Your browser does not support embedded video. <a href="{{ '/assets/video/cookability/cookability-demo.mp4' | relative_url }}">Watch the Cookability demo.</a>
        </video>
    </div>
</div>
<div class="caption">
    A full walkthrough of Cookability.
</div>

## Your recipes and something new

Recipes can be entered by hand, pasted as text, or imported from a link or a text-based PDF. A searchable library keeps them together, while favorites help shape future recommendations. Discover offers three starting points: Surprise me, What are you in the mood for?, and What's in your fridge?

<div class="row">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/cookability/home-screen.jpg" title="Recipe library" alt="Cookability recipe library with search, an Add a recipe button, and recipe cards" class="img-fluid rounded z-depth-1" caption="Keep recipes together in a searchable library with photos, cooking times, and servings." %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/cookability/discover.jpg" title="Discover recipes" alt="Discover screen offering Surprise me, What are you in the mood for, and What's in your fridge" class="img-fluid rounded z-depth-1" caption="Explore three ways to find your next dish, using your own recipe library as a starting point." %}
    </div>
</div>

## What should I cook tonight?

The mood flow asks about cuisine, recent meals, and available cooking time to suggest something that fits the evening. The fridge flow starts with ingredients you have on hand, ranks saved recipes by ingredient coverage, and suggests new dishes. Missing ingredients can be added to the shopping list.

<div class="row">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/cookability/mood.jpg" title="Choose what sounds good" alt="Cuisine choices, yesterday's meal input, and cooking-time preferences in Cookability" class="img-fluid rounded z-depth-1" caption="Choose cuisines and cooking time, and note recent meals to help avoid repeats." %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/cookability/fridge.jpg" title="What's in your fridge?" alt="Ingredient entry screen with an Add button and selectable ingredients from saved recipes" class="img-fluid rounded z-depth-1" caption="Enter ingredients or select them from your recipes to find dishes with fewer things to buy." %}
    </div>
</div>

## From a recipe to dinner

When an ingredient is missing, Cookability offers substitutions grounded in the recipe, with explanations of how each change affects the dish. Applying suggestions saves a new variation and labels the changes, preserving the original recipe.

Cooking mode provides large, step-by-step directions, timers, and hands-free voice commands. Servings scale with exact fractions, and the shopping list combines duplicate ingredients across recipes.

## How it was built

Cookability uses React Native and TypeScript with SQLite for recipe storage. A separate TypeScript domain layer handles ingredient parsing, exact quantity calculations, and recipe variations. AI responses are validated against structured schemas before they reach the interface, and a server-side proxy keeps API keys out of the app. Native modules support PDF text extraction and recipe-photo storage, while speech recognition and text-to-speech support hands-free cooking.
