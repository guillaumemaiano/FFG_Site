---
title: "From Design Tokens to Takeoff"
date: 2026-07-09
journal_number : 2
draft: false
description: "Building the design system before designing the website."
featured_image: "images/journal/french-industrial-art-deco-hero.png"
---

# From Design Tokens to Takeoff

> Read Part 1: [Deriving a Visual Language](../post1)

---

## Design Log

### Why Tokens Before Design?

See Part 1 for how we arrived at French Industrial Art Deco.

This post documents what came next: **making it real.**

From pilots to masons to musicians, one lesson resonates. Masters of the craft make planes, violins, and rock sound a symphony.

Soul can only come once the bricks exist.

Typography is visible, but it depends on everything around it. Colors, spacing, borders, elevations—all need to be decided first.

Only then does choosing a font become intentional rather than arbitrary.

### Design Tokens

Rather than immediately writing CSS, we built a common vocabulary.

Colors became semantic roles instead of hexadecimal values. Typography, spacing, elevations and layout widths all received reusable names.

You can inspect the actual token definitions in [`tokens.css`](https://github.com/guillaumemaiano/FFG_Site/blob/main/hugo/themes/IndustrialOptimism/assets/css/tokens.css):

```css
:root {
  --color-midnight-blue: #0d1b2a;
  --color-brass: #c8a24b;
  --font-heading: "Marcellus", serif;
  --font-body: "B612", sans-serif;
  --border-base: color-mix(in srgb, var(--color-midnight-blue) 18%, transparent);
}
```

The goal wasn't to freeze the design forever.

It was to create a stable foundation that every future page could build upon without duplicating decisions.

### Building the System

Once the design vocabulary existed, we started reorganizing the Hugo theme itself.

Shared partials became cleaner, common layout rules became reusable, and we began moving away from page-specific styling.

The full theme is open-source at [IndustrialOptimism](https://github.com/guillaumemaiano/FFG_Site/tree/main/hugo/themes/IndustrialOptimism).

Interestingly, most of the work remained invisible.

The website barely looked different.

The codebase, however, became considerably easier to evolve.

---

## Engineering Log

In the previous step, we built a Hugo site we serve locally using `hugo server`.

How very comfortable. How very "risk-free".

Nobody sees it. Nobody criticizes it.

So we're going to fix that. Let's get online. Let's get dirty.

REX in progress.

### GitHub Pages

Publishing the site turned out to be much simpler than expected.

GitHub Pages integrates naturally with Hugo, making it possible to publish every commit almost immediately.

Getting online also changes the mindset.

A local website is a prototype.

A public website is a promise.

### Custom Domain

The final step was giving the project its own identity on the Internet.

Configuring the custom domain involved the usual DNS records, propagation delays and a fair amount of waiting.

Nothing particularly difficult.

Just enough to remind us that the Internet still has a few moving parts.

With that done, Flying Fortress Games finally exists somewhere other than a local development machine.

{{< image
  src="images/journal/french-industrial-art-deco-hero.png"
  alt="French Industrial Art Deco homepage hero featuring ocean liner with brass accents and Art Deco framing"
  class="journal-image"
>}}

> French Industrial Art Deco. Engineered worlds. Stories that endure.

---

### What's Next

The bricks are laid.

Now comes the harder work: making them sing.

That's where soul enters. Not before. Not after. Once the foundation holds.

### Future Work

At some point, I'll have to look into security: signed commits with GPG. Always keep some nerdy wrench manipulation handy, should you ever feel a bit too artistic. You know... Dirt. Grit. Oil.

---