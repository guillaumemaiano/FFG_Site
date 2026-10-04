# 1. Art Direction

**French Industrial Art Deco**

### Atmosphere

**Engineering + culture**

An elegant technical institution identity characterized by **industrial optimism**.

---

## Moodboard Color Palette

| Role | Color | Hex |
|------|------:|----:|
| Midnight Blue | Primary / Background | `#0D1B2A` |
| Ivory | Light Background | `#F2EFE6` |
| Brushed Brass | Primary Accent | `#C8A24B` |
| Slate Grey | Technical Neutral | `#3B4754` |
| Walnut | Warm Material | `#5A3A22` |
| Ocean Blue | Secondary Accent | `#1E3A4A` |

The implementation separates these raw palette values from the semantic color roles consumed by components.

The raw palette therefore defines available materials; tokens such as `--surface-page`, `--text-main` and `--accent-primary` define how those materials are used.

---

## Moodboard Typography

| Usage | Font |
|------|------|
| Headings | **Marcellus** |
| Body | **B612** |
| Project taglines | **Source Sans 3** |
| Code / Technical Notes | **IBM Plex Mono** |

The original moodboard specified **Gill Sans** for body text.

During implementation, the principal body role subsequently moved to **B612**, with Source Sans 3, PT Sans, Gill Sans and system-compatible faces retained in the fallback stack.

Typography is exposed to components through semantic font roles rather than by repeatedly specifying concrete font families.

---

## Identity Elements to Preserve

- midnight blue / ivory / brushed brass / walnut palette;
- dark surfaces contrasted with warm paper backgrounds;
- elegant serif + highly legible sans-serif + technical monospace typography;
- fine line iconography;
- restrained Art Deco ornamentation;
- structured grid layout;
- an atmosphere of **cultivated engineering**.

---

# 2. Typography Direction

The selected typography conveys elegance, institutional heritage and confidence.

The principal typography is now established as:

- **Marcellus** for principal headings and display typography;
- **B612** for general body and interface typography;
- **Source Sans 3** for project taglines and selected supporting roles;
- **IBM Plex Mono** for technical, metadata and code-like presentation.

Typography is implemented through semantic design tokens so that changes to the underlying families need not require changes to individual components.

## Evaluation Record

The earlier heading evaluation considered the following alternatives:

| Option | Effect |
|--------|--------|
| **Marcellus** | More architectural, more Art Deco, stronger presence |
| **Cormorant Garamond** | More literary, more salon-inspired, more historical |
| **Source Serif 4** | More restrained, more contemporary, more readable |
| **Cinzel** | More monumental, but risks becoming overly grandiose |
| **Cormorant SC** | Suitable for small labels or accents, not for general use |

The intended evaluation method used the **same hero section**, **same colors**, and **same layout**, varying only the heading typeface between:

- Marcellus;
- Cormorant Garamond;
- Source Serif 4.

Marcellus emerged as the principal heading face and remains the first choice in the current heading stack.

---

# 3. Implementation Strategy

## Current Stack

The website currently uses:

- GitHub Pages deployment through GitHub Actions;
- Hugo;
- the `IndustrialOptimism` Hugo theme;
- Tailwind CSS 4;
- Hugo's Tailwind CSS processing pipeline;
- semantic Hugo templates;
- custom CSS backed by CSS custom properties.

Hugo was originally selected because it is well suited to a static site containing project pages, a development journal/blog, taxonomies, RSS feeds, and automated deployment through GitHub Pages.

Those capabilities remain consistent with the current direction of the site.

Tailwind is operational in the build pipeline, but the website is **not authored as a utility-first Tailwind application**.

There is currently no established dependency on:

- a Tailwind `@theme` design-system layer;
- an `@apply` component architecture;
- widespread Tailwind utility classes in the Hugo templates.

This is intentional.

The Flying Fortress Games design system remains independent of the CSS framework.

---

## Current Architecture

The implementation is organized approximately as follows:

```txt
hugo/
├─ content/
│  ├─ projects/
│  ├─ journal/
│  └─ static content pages
│
├─ assets/
│  └─ images/
│
├─ themes/
│  └─ IndustrialOptimism/
│     ├─ layouts/
│     │  ├─ baseof.html
│     │  ├─ home.html
│     │  ├─ page.html
│     │  ├─ list.html
│     │  ├─ single.html
│     │  ├─ section.html
│     │  ├─ taxonomy.html
│     │  ├─ term.html
│     │  ├─ in-dev.html
│     │  ├─ journal/
│     │  ├─ projects/
│     │  ├─ _partials/
│     │  └─ _shortcodes/
│     │
│     ├─ assets/
│     │  └─ css/
│     │     ├─ tokens.css
│     │     ├─ main.css
│     │     └─ components/
│     │
│     └─ static/
│        └─ fonts/
│
└─ hugo.toml
```

The structure should evolve only where stable implementation boundaries have emerged.

Architecture should follow the implementation rather than anticipate hypothetical abstractions.

---

## CSS Strategy

The CSS architecture follows these rules:

- `tokens.css` is the framework-neutral source of truth for the design system;
- semantic CSS classes remain the normal way to express component and page intent;
- Hugo templates remain readable and semantic;
- global tokens represent stable, reusable design roles;
- page-specific and component-specific values remain local until broader reuse is demonstrated;
- Tailwind may consume selected design-system values where it provides a concrete benefit;
- Tailwind adoption does not justify rewriting working semantic CSS;
- heavy component frameworks are avoided;
- abstraction follows demonstrated reuse rather than anticipated reuse.

Tailwind therefore complements the existing CSS architecture rather than replacing it.

Large-scale conversion of the current site to utility classes is explicitly not a goal.

---

## Established Presentation Surfaces

The implementation now contains several distinct, validated presentation surfaces rather than the speculative generic component set envisioned during initial planning.

These include:

- persistent site header and navigation;
- footer;
- homepage featured-project and journal presentation;
- journal article layout;
- engineering-style journal/devlog presentation;
- project hero;
- projects carousel and lateral indicators;
- project dossier and side-panel treatment;
- in-development placeholder;
- 404 presentation;
- responsive adaptations of these surfaces.

Shared abstractions should be introduced where these surfaces demonstrate genuine common structure.

Visually similar elements should not automatically be merged when their behavior or semantic role differs.

### Original component proposal

Initial planning proposed a small set of generic reusable components:

- `Hero`;
- `ProjectCard`;
- `DispatchCard`;
- `Footer`;
- `Button`;
- `SectionTitle`.

This list is retained as design history rather than as a current implementation requirement.

The site evolved toward more specific presentation surfaces. Future component extraction should therefore follow demonstrated reuse rather than the original speculative component list.

---

# 4. Visual Grammar

## Overall Composition

The visual language is based on a strong alternation between dark and light sections, creating a clear reading rhythm while emphasizing hierarchy.

The overall impression should be structured, calm and confident.

---

## Decorative Language

- thin Art Deco corner ornaments;
- geometric framing;
- fine brass separators;
- restrained decorative rules.

Decoration frames the content rather than competing with it.

---

## Material Language

The visual identity draws upon:

- brass;
- enamel;
- steel;
- walnut;
- glass.

These materials suggest craftsmanship and engineering without becoming nostalgic.

---

## Color Hierarchy

Colors have distinct semantic roles.

| Color | Function |
|--------|----------|
| Midnight Blue | Authority, structure, primary dark surfaces |
| Ivory | Reading surfaces and breathing space |
| Brushed Brass | Emphasis, interaction and highlights |
| Walnut | Warmth and materiality |
| Slate Grey | Technical neutral |
| Ocean Blue | Secondary accent |

Individual projects may introduce their own theme colors where appropriate, but those colors supplement rather than replace the global Flying Fortress Games identity.

---

## Photography and Imagery Direction

Photography should consistently convey:

- engineering;
- exploration;
- craftsmanship;
- infrastructure.

Images should favor:

- warm natural light;
- restrained saturation;
- cinematic composition;
- premium materials.

Illustrative and project-specific artwork may develop its own visual language where required by the work being presented.

Image content is therefore flexible while its presentation remains governed by the broader site composition.

---

## Brand Tone

> **Elegance in design. Engineering in every detail.**

---

## Design Principle

Visual identity shall be expressed primarily through:

- color;
- typography;
- composition;
- materials.

Content imagery is illustrative rather than prescriptive and may evolve without altering the brand identity.

---

# 5. Design-System Direction

The implementation shall preserve a clear separation between:

1. the **Flying Fortress Games design system**;
2. semantic CSS and component presentation;
3. Hugo content and templates;
4. Tailwind CSS as an optional implementation tool.

The design system is not defined by Tailwind.

Its canonical vocabulary is expressed through the CSS custom properties maintained in `tokens.css`.

Tailwind may consume selected primitives or semantic roles where doing so improves implementation, but framework conventions must not silently redefine existing FFG semantics.

Particular care is required around existing namespaces such as:

- `--text-*`;
- `--radius-*`;
- `--ease-*`.

Any reconciliation of these namespaces with Tailwind belongs to a separate technical pass.

The current architecture therefore favors:

- semantic intent;
- stable design tokens;
- readable templates;
- specialized CSS where it expresses the design clearly;
- evidence-driven abstraction;
- minimal framework coupling.

Framework adoption is a means to improve implementation, not a design objective in itself.
