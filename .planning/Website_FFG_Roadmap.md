# Flying Fortress Games Website Roadmap (Version 0.2)

## Purpose

This document defines the implementation roadmap for the first version of the Flying Fortress Games website.

The objective is to establish a complete, reusable design system and implement a functional website based upon it.

---

# Engineering Status — 2026-10-01

This section records the current implementation state.

The original roadmap below is retained as the historical implementation plan. It should not be retroactively rewritten merely because the implementation has evolved.

## Current Baseline

The website is now substantially beyond the initial foundation stage.

The current implementation uses:

- Hugo `0.164.0`;
- GitHub Pages deployment through GitHub Actions;
- Tailwind CSS `4.3.2`;
- Hugo's `css.TailwindCSS` processing pipeline;
- the `IndustrialOptimism` Hugo theme;
- semantic Hugo templates backed primarily by custom CSS classes and CSS custom properties.

Tailwind is operational in the build pipeline, but the site is **not currently authored as a utility-first Tailwind application**.

There is presently no established:

- `@theme` integration layer;
- `@apply` component architecture;
- significant use of Tailwind utility classes in templates.

This distinction is intentional to preserve the design system independently of any particular CSS framework.

## Design System State

The design-token system has grown substantially beyond the original palette and spacing definitions.

`tokens.css` currently acts as the framework-neutral source of truth for:

- raw color palettes;
- website semantic colors;
- engineering-document semantic colors;
- border roles;
- typography families;
- document typography roles;
- project typography roles;
- type scale;
- spacing scale;
- layout dimensions;
- header and project geometry;
- border widths and radii;
- elevation;
- image treatments;
- interaction timing and motion.

Components and page layouts consume these semantic values rather than defining their own design language.

This remains consistent with the original principle:

> Tokens capture semantic intent, not implementation.

## Implemented Site Surfaces

The implementation currently includes, among other work:

- persistent site header and navigation;
- site footer and external/institutional links;
- responsive behavior across the principal layouts;
- journal article presentation;
- engineering-style devlog index;
- RSS integration;
- project presentation;
- project hero and dossier layouts;
- project carousel and lateral navigation;
- project-specific visual tones and theme colors;
- responsive project navigation;
- homepage selection of featured project content and recent journal content;
- Art Deco framing and visual accents;
- local font assets and semantic typography roles.

The implementation has therefore moved beyond the original linear sequence of the roadmap. Several later-phase concerns were developed while earlier elements were still being refined.

## Current Technical Assessment

The framework-neutral token architecture has proven useful and should be preserved.

Tailwind should therefore be treated as a **consumer of the Flying Fortress Games design system**, not as the owner of that system.

The existing CSS custom properties remain the canonical design vocabulary.

A future Tailwind integration may expose selected primitives or roles where doing so provides concrete value, but migration to Tailwind syntax is not itself an objective.

## Immediate Engineering Priorities

### 1. Debris Cleanup

Perform a behavior-neutral cleanup pass.

Review and remove only demonstrably obsolete or duplicated material, including:

- duplicated token definitions;
- temporary experimentation comments;
- redundant declarations;
- obsolete prototype styling;
- unused selectors or variables after usage verification;
- development documentation that no longer reflects the actual build pipeline.

No visual redesign should be combined with this pass.

### 2. Tailwind Strategy Documentation

Update the technical/design documentation to define the intended relationship between:

- Flying Fortress Games design tokens;
- semantic CSS;
- Tailwind CSS;
- Hugo templates.

The central architectural principle shall be:

> The FFG design system remains framework-neutral. Tailwind may consume it where useful.

### 3. Tailwind Preparation

After the strategy has been documented, perform a compatibility cleanup before introducing broader Tailwind usage.

Particular attention is required for token namespaces which overlap with Tailwind theme namespaces, including:

- `--text-*`;
- `--radius-*`;
- `--ease-*`.

Existing tokens must not be mechanically converted. Naming and meaning should be reconciled deliberately so that future Tailwind integration cannot silently change existing semantics.

### 4. Controlled Tailwind Adoption

Only after the cleanup and preparation work should Tailwind utilities or theme integration be introduced more broadly.

Adoption should be incremental and justified by demonstrated benefit.

Semantic templates and specialized visual CSS should remain valid where they express the design more clearly than utility composition.

Large-scale conversion of existing working CSS is explicitly not a goal.

## Maintenance Direction

`main.css` has grown considerably as the site matured.

Further decomposition should happen only where stable component or page boundaries have emerged.

The project should continue to prefer:

1. semantic intent;
2. stable design tokens;
3. readable templates;
4. evidence-driven abstraction;
5. minimal framework coupling.

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
