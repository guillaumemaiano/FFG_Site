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

---

## Moodboard Typography

| Usage | Font |
|------|------|
| Headings | **Marcellus** |
| Body | **Gill Sans** |
| Code / Technical Notes | **IBM Plex Mono** |

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

# 2. Typography Evaluation

The selected typography immediately conveys elegance, institutional heritage and confidence.

The heading typeface deserves a final validation before becoming part of the permanent visual identity.

The following alternatives should be compared under identical conditions.

| Option | Effect |
|--------|--------|
| **Marcellus** | More architectural, more Art Deco, stronger presence |
| **Cormorant Garamond** | More literary, more salon-inspired, more historical |
| **Source Serif 4** | More restrained, more contemporary, more readable |
| **Cinzel** | More monumental, but risks becoming overly grandiose |
| **Cormorant SC** | Suitable for small labels or accents, not for general use |

The typography evaluation should be straightforward.

Use the **same hero section**, **same colors**, and **same layout**, varying only the heading typeface between:

- Marcellus
- Cormorant Garamond
- Source Serif 4

---

# 3. Implementation Strategy

**Planned stack**

- GitHub Pages
- Hugo
- Tailwind CSS

Hugo is particularly well suited to a static website containing project pages, a development blog, tags, RSS feeds, and automated deployment through GitHub Pages.

Tailwind CSS integrates cleanly with Hugo while remaining unobtrusive, allowing the project to rely primarily on semantic HTML and lightweight custom components.

## Minimal Architecture

```txt
ffg-site/
├─ content/
│  ├─ projects/
│  ├─ dispatches/
│  └─ pages/
├─ layouts/
│  ├─ index.html
│  ├─ partials/
│  └─ _default/
├─ assets/
│  └─ css/
├─ static/
│  └─ images/
└─ hugo.toml
```

## CSS Strategy

- define the color palette using CSS variables;
- use Tailwind primarily for layout, spacing and responsive behavior;
- avoid heavy component frameworks;
- implement a small set of reusable custom components:
  - `Hero`
  - `ProjectCard`
  - `DispatchCard`
  - `Footer`
  - `Button`
  - `SectionTitle`

---

# 4. Visual Grammar

## Overall Composition

The visual language is based on a strong alternation between dark and light sections, creating a clear reading rhythm while emphasizing hierarchy.

The overall impression should be structured, calm and confident.

## Decorative Language

- thin Art Deco corner ornaments;
- geometric framing;
- fine brass separators;
- restrained decorative rules.

Decoration frames the content rather than competing with it.

## Material Language

The visual identity draws upon:

- brass;
- enamel;
- steel;
- walnut;
- glass.

These materials suggest craftsmanship and engineering without becoming nostalgic.

## Color Hierarchy

Colors have distinct semantic roles.

| Color | Function |
|--------|----------|
| Midnight Blue | Authority, structure, primary surfaces |
| Ivory | Reading surfaces and breathing space |
| Brushed Brass | Emphasis, interaction and highlights |
| Walnut | Warmth and materiality |
| Slate Grey | Technical neutral |
| Ocean Blue | Secondary accent |

## Photography Direction

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

## Brand Tone

> **Elegance in design. Engineering in every detail.**

## Design Principle

Visual identity shall be expressed primarily through:

- color,
- typography,
- composition,
- materials.

Content imagery is illustrative rather than prescriptive and may evolve without altering the brand identity.