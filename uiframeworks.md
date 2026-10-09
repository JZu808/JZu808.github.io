---
layout: essay
type: essay
title: "Somebody Already Built Your Navbar"
# All dates must be YYYY-MM-DD format!
date: 2026-10-08
published: true
labels:
  - Software Engineering
  - Bootstrap
  - CSS
image: /img/bootstrap-5.0-illustration.png
---

## The Navbar Problem

A navbar seems easy. It's just a row of links.

Then you build one from scratch. The links line up fine on a laptop, but on a phone they run off the screen. So you add a media query. Then you need a menu button, which needs JavaScript. Then the menu covers the page content. An hour later, you have a navbar that works on the two browsers you tested.

Here is the same navbar in Bootstrap 5:

```html
<nav class="navbar navbar-expand-lg bg-body-tertiary">
  <div class="container">
    <a class="navbar-brand" href="#">My Site</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#nav">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="nav">
      <ul class="navbar-nav">
        <li class="nav-item"><a class="nav-link" href="#">Projects</a></li>
        <li class="nav-item"><a class="nav-link" href="#">Essays</a></li>
      </ul>
    </div>
  </div>
</nav>
```

It works on phones, the menu button works, and it has already been tested on many browsers. That's the main reason to use a UI framework: someone already built the common parts for you.

## Why Not Just Use HTML and CSS?

Bootstrap takes time to learn. There's the grid system, screen size names, and hundreds of class names. It can feel like learning a new language. So why not just use plain HTML and CSS?

I've done it the plain way. This summer, at my internship with the Hawaii Department of Transportation, I built a project scoring tool with only HTML, CSS, and JavaScript. Writing the logic was the fun part. But I spent a lot of time on CSS, like spacing, table styles, and getting things to line up.

A framework doesn't replace CSS. It makes a lot of small styling choices for you, so you can focus on the parts of the project that matter.

## A Simple Example

Say you want a grid of cards: one column on phones, two on tablets, and three on laptops. In plain CSS:

```css
.card-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
}
@media (min-width: 768px) {
  .card-grid { grid-template-columns: repeat(2, 1fr); }
}
@media (min-width: 992px) {
  .card-grid { grid-template-columns: repeat(3, 1fr); }
}
.card {
  border: 1px solid #dee2e6;
  border-radius: 0.375rem;
  padding: 1rem;
}
```

In Bootstrap:

```html
<div class="container">
  <div class="row g-3">
    <div class="col-12 col-md-6 col-lg-4">
      <div class="card"><div class="card-body">Card one</div></div>
    </div>
    <!-- more cards -->
  </div>
</div>
```

The plain CSS isn't hard. But a real website has dozens of pieces like this, and each one needs its own sizes, colors, and spacing. The 768px and 992px in my CSS are the same sizes Bootstrap uses. Write enough CSS yourself and you end up rebuilding a framework anyway.

## Why It's Worth Learning

Yes, Bootstrap is like a new language. That's actually what makes it useful.

When I see `col-md-6`, I know it means half the width on medium screens and up. Any developer who knows Bootstrap knows that too. Class names like `mt-3`, `d-flex`, and `btn btn-primary` mean the same thing on every project. A teammate can read my HTML and understand the layout without reading a stylesheet I made up.

That's why UI frameworks matter for software engineering. Good code is code other people can read and change. A framework helps with that:

- **Consistency.** Buttons, forms, and spacing all look the same across the site.
- **Teamwork.** Everyone on the team uses the same class names.
- **Testing.** The framework already works across browsers and screen sizes.
- **Documentation.** When something breaks, you can look it up.

In other words, decide something once, in one place. A framework does that for design.

## The Downsides

Frameworks have real costs too.

**Messy HTML.** Bootstrap code can get long. One `div` might have `d-flex justify-content-between align-items-center mb-3 px-2`. It works, but it's hard to read.

**Every site looks the same.** If you use the defaults, your site looks like a lot of other sites. Changing that means overriding Bootstrap's styles, which can be frustrating.

**Updates can break things.** When Bootstrap went from version 4 to 5, some class names changed, like `ml-3` to `ms-3` and `data-toggle` to `data-bs-toggle`. Old tutorials and copied code stopped working right.

## My Experience with Bootstrap 5

My most recent Bootstrap 5 project so far was recreating the homepage of Banyans Craft Kitchen and Lounge, a restaurant in Kailua. The page had three parts: a navbar with the logo and menu links, large centered text over a background photo, and a footer with the location, hours, and an email signup.
 
Getting the basic layout done was faster than I expected. The grid made it easy to split the footer into columns. I used uneven widths (`col-2`, `col-1`, `col-5`, `col-1`, `col-3`) so the business hours had enough room. In plain CSS, that would have taken a lot more trial and error.
 
The hard part was matching the mockup exactly. I wanted the menu links to change color, but my changes didn't show up at first. The problem was that the `nav-link` class needed to be on the `<a>` tag, not the `<li>`. Centering the hero text was also tricky. My first tries either didn't center the text or added a sideways scroll bar. Using `flex-grow-1` on the middle row and `mx-0` to remove the row's side margins fixed both.
 
The part that sold me was the hamburger menu. The mockup showed the links folding into a three-line button on small screens. I added `navbar-expand-lg`, a toggler button, and the Bootstrap JavaScript file, and it just worked. Making the links turn blue on hover only took one CSS variable, `--bs-nav-link-hover-color`. That's basically the navbar from the start of this essay, and it's the main reason I think Bootstrap is worth learning.

## So Which One Should You Use?

Use a framework when other people will work on the site or when it needs to look good on different screens. That covers group projects, portfolios, and anything you'll keep updating. For a small one-time page or a very custom design, plain CSS is fine.

Either way, knowledge of CSS is stil needed. Bootstrap is built on flexbox, grid, and media queries. Knowing those helps you change Bootstrap when the defaults don't fit.

Learning Bootstrap takes time, but it teaches you how teams build websites: agree on one system and build on top of it. That's worth the effort.

## AI Use

I used Claude to help draft and organize this essay, and stylize the format.
