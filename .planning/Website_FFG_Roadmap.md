# Flying Fortress Games Website Roadmap (Version 0.1)

## Purpose

This document defines the implementation roadmap for the first version of the Flying Fortress Games website.

The objective is to establish a complete, reusable design system and implement a functional website based upon it.

---

# Phase I — Foundations

## Step 1 — Create the Repository

- Create the `ffg-website` repository.
- Enable GitHub Pages.
- Initialize Hugo.
- Configure Tailwind CSS.

**Deliverable**

- Website builds successfully in a local environment.

---

## Step 2 — Define Design Tokens

Create the global design system.

Define:

- Color palette
- Typography
- Border radius
- Shadows
- Borders
- Spacing scale
- Responsive breakpoints

Implement the design tokens as:

- CSS variables (`design-tokens.css` or equivalent)
- Tailwind theme configuration

**Deliverable**

- Centralized design token system.

---

## Step 3 — Install Candidate Typefaces

Install the candidate typefaces for evaluation.

Candidates:

- Marcellus
- Cormorant Garamond
- Source Serif 4
- Gill Sans (or temporary fallback)
- IBM Plex Mono

---

## Step 4 — Typography Evaluation

Compare the candidate heading typefaces under identical conditions.

The comparison shall use:

- the same Hero section;
- the same layout;
- the same colors;
- the same content.

Only the heading typeface shall vary.

Evaluate:

- Marcellus
- Cormorant Garamond
- Source Serif 4

---

## Step 5 — Freeze Typography

Select the permanent typography stack.

Create semantic typography classes.

Examples:

```css
.hero-title
.section-title
.body
.caption
.code
```

---

## Step 6 — Build the Layout Grid

Implement the global layout system.

Define:

- Containers
- Columns
- Responsive behavior
- Section spacing

---

# Phase II — Core Components

## Step 7 — Buttons

Create:

- Primary button
- Secondary button
- Text link

---

## Step 8 — Cards

Create a reusable card component.

Future uses include:

- Project cards
- Article cards
- Video cards

---

## Step 9 — Navigation

Create the primary navigation.

Include:

- Logo
- Navigation menu
- Placeholder for future language selector

---

## Step 10 — Footer

Create the footer component.

Include:

- Social links
- Copyright
- Secondary navigation

---

# Phase III — Visual Identity

## Step 11 — Apply the Color Palette

Integrate the selected palette throughout the design system.

Colors:

- Midnight Blue
- Ivory
- Brushed Brass
- Walnut
- Slate Grey
- Ocean Blue

---

## Step 12 — Decorative Elements

Implement the decorative language.

Include:

- Art Deco corner ornaments
- Thin separators
- Brass accents

---

## Step 13 — Imagery

Integrate temporary imagery to validate:

- Composition
- Cropping
- Color grading

---

# Phase IV — Homepage

## Step 14 — Hero Section

Create the homepage hero.

Include:

- Logo
- Tagline
- Primary call-to-action

---

## Step 15 — Featured Project

Create the featured project section.

Display:

- One featured project

---

## Step 16 — Latest Dispatch

Create the latest dispatch section.

Display:

- One recent article or devlog

---

## Step 17 — Footer Integration

Complete homepage integration.

Verify navigation and footer links.

---

# Phase V — Content Templates

## Step 18 — Project Template

Create the Hugo template for projects.

Location:

```text
content/projects/
```

Fields:

- Title
- Status
- Summary
- Hero image

---

## Step 19 — Dispatch Template

Create the template for:

- Development logs
- Engineering articles

Also create the remaining static pages:

- About
- Contact
- Privacy Policy

---

# Phase VI — Validation

## Step 20 — Brand Validation

Review the complete implementation.

Verify consistency across:

- Typography
- Color palette
- Components
- Layout
- Visual identity

Validate responsiveness on:

- Desktop
- Tablet
- Mobile

The result shall constitute **Version 0.1** of the Flying Fortress Games website.