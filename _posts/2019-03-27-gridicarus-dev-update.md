---
layout: post
title: "Gridicarus: Development Update #2"
category: project
published: true
---

Gridicarus is back and cleaner than ever! It's been about a year since the last patch,
mostly because *(I thought)* I liked how the project ended up and also couldn't be bothered to update the dependencies.
However! One of the projects I'm working on could use Gridicarus' help, so I decided to update it... and what I found was shocking! If you don't care about the changes and just want to know what I'm talking about, [click here](https://0px.moe/gridicarus/).

### Awkward syntax

In the original version, to create a grid you'd use `grid-parent` on the main element, and `grid-child` on every child of said grid. This doesn't make very much sense as everything inside `grid-parent` is automatically a child by semantics. That convention has been replaced by just using `parent` on the main element, and nothing on the children. Now the children only worry about their size and shape in the grid, rather than if they're even a child!

And that brings me to how children in the grid were shaped and arranged. Originally, I thought it would be cool to do some weird `grid-child #1` type syntax and really *stretch* the limits of HTML and CSS. This was dumb, made no sense semantically, and actually raised errors in the console *(can you tell I extensively tested this?)*. This has been replaced by a single `order-(1-16)` class which explains everything it needs to in one word and one number (and one dash).

### Inconsistency

Gridicarus' syntax is much more consistent now. Dashes are more prevalent in the framework now too. For example, in the original version, this is valid:
```
<div class="grid-parent">

  <div class="grid-child #1 h-span2 box-lime">
    Header
  </div>
  <div class="grid-child #2 h-span2 box-blue">
    Body
  </div>
  <div class="grid-child4 box-grey">
    Footer Left
  </div>
  <div class="grid-child4 box-silver">
    Footer Right
  </div>

</div>
```

Sure *this* is "consistent," but it's ugly. *Why are there dashes between everything* ***but*** *numbers?* *Why do you have the option to use* `grid-child4` *and* `grid-child #4` *?* *Why do you get so many options in the first place? Isn't that just confusing?*  All of these were questions I had for myself when reading through the source code and documentation again. And that brings me to one of the things I've been slowly discovering for myself:

> Syntax shouldn't try to accommodate multiple styles. It should accommodate one style incredibly well.

I'm sure this quote has been said a million times by a million different people, but it's now the mindset for Gridicarus. Anything legacy has been removed in favor of the new, better style.


### Responsivity(?) Responsiveness(?)

The original version featured nothing to help with responsive design. Goodbye chances of making anything for multiple platforms *(what's mobile?)*. The newest version has a little bit to help in responsive design. Enough to make a website that looks good on desktop, and can transitions to mobile without any loss in functionality. I do plan on adding more things, such as proper templating, responsive resizing, etc. However, I'm faced with a bit of a dilemma. I can either,

  * **accommodate all types of responsivity** (every breakpoint, every necessary change);
    * Bulkier---and possibly---more confusing framework, destroyer of `npm install`.
  * **accommodate some types of responsivity** (resize rows by x on tablet) *(current)*;
    * Regular-sized framework, a little bit of heaviness but nothing too crazy.
  * **say "Hey, you got this one" and do nothing!**
    * Super cool, totally minimal, Bauhaus-inspired, Ikea framework

I haven't fully committed to any of them, yet. I'd prefer the framework to be lightweight, almost like a blank canvas for you to add onto. But at the same time, I want it to have enough features so that it's even worth using. I mean, what's the point of using a framework you can easily write yourself in 10 minutes? This is something I need to think about more.


### In closing

My main goal for Gridicarus has been, and will always be for it to be a framework that allows people to use the awesomeness that is CSS Grids, easily. At this point, I'm actually happy with Gridicarus. Not happy enough to stop working on it, but happy enough to use it and not be like *"Wow this sucks, I'll just use [insert other framework here]."* --- If you'd like to check out the project, you can do that [here](https://0px.moe/gridicarus/).

Thank you for reading through my rant and revival of a year old project.

Stay well,  
-- Judah
