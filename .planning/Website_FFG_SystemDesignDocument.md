# Design Tokens — Abstraction Rules

The Flying Fortress Games design system is **framework-neutral**.

Design tokens capture stable design intent. Values may evolve while their usages remain stable.

The canonical implementation currently lives in:

`hugo/themes/IndustrialOptimism/assets/css/tokens.css`

Tailwind CSS may consume selected parts of this system where useful, but it does not own the Flying Fortress Games design vocabulary.

---

## Token Layers

The token system contains two principal layers.

### Primitive tokens

Primitive tokens describe concrete design values.

Examples include:

- raw palette colors such as `--color-midnight-blue`;
- type sizes;
- spacing values;
- radii;
- elevation values.

Primitive names may describe their actual value or visual characteristic.

### Semantic tokens

Semantic tokens describe a role in the interface.

Examples include:

- `--surface-page`;
- `--text-main`;
- `--accent-primary`;
- `--document-text`;
- `--project-font-title`.

Components should prefer semantic tokens where a meaningful semantic role exists.

A primitive should not be promoted into a semantic abstraction merely because it has been used once.

---

## Colors

### Raw palette (`--color-*`)

The raw palette defines concrete colors available to the design system.

The principal website palette includes:

- `--color-midnight-blue`;
- `--color-ivory`;
- `--color-brass`;
- `--color-slate`;
- `--color-walnut`;
- `--color-ocean-blue`.

The engineering-document palette uses its own raw primitives:

- `--color-document-paper`;
- `--color-document-ink`;
- `--color-document-grey`;
- `--color-document-rule`.

Raw palette values are implementation primitives, not component roles.

### Website semantic colors

Website components should normally consume role-based tokens.

| Token | Role |
| --- | --- |
| `--surface-page` | Principal light surface |
| `--surface-panel` | Panel surface |
| `--container-bg` | Principal dark structural surface |
| `--text-main` | Primary text |
| `--text-muted` | Secondary or subdued text |
| `--accent-primary` | Primary accent and emphasis |
| `--accent-secondary` | Secondary accent |

### Engineering-document semantic colors

The engineering-document and devlog presentation uses a distinct semantic layer.

| Token | Role |
| --- | --- |
| `--document-surface` | Document surface |
| `--document-text` | Primary document text |
| `--document-text-muted` | Secondary document text |
| `--document-rule` | Structural rules |
| `--document-link` | Document links |
| `--document-link-hover` | Document link interaction |

Semantic names describe purpose rather than appearance.

Semantic tokens should avoid appearance-based names such as `--blue`, `--gold`, or `--dark-gray`. Appearance-based naming is appropriate for primitive palette values.

---

## Borders (`--border-*`)

Structural and interaction boundaries.

| Token | Use Case |
| --- | --- |
| `--border-width` | Standard structural border width |
| `--border-base` | Passive separators |
| `--border-interactive` | Clickable or actionable boundaries |
| `--border-highlight` | Emphasized states such as hover, focus or active |

These roles are independent. Their current values may share visual characteristics, but no dependency between them should be assumed.

Token names reflect purpose, not color.

---

## Typography

### Font roles (`--font-*`)

Typography tokens describe editorial function rather than concrete typefaces.

| Token | Role |
| --- | --- |
| `--font-heading` | Principal display and heading typography |
| `--font-body` | General reading and interface text |
| `--font-code` | Technical, metadata and monospace content |
| `--font-project-tagline` | Project tagline typography |

Changes to the underlying typography should normally be made through the appropriate role token so that consuming components remain unchanged.

### Engineering-document roles

Engineering-document presentation provides more specialized semantic roles:

- `--document-font-title`;
- `--document-font-text`;
- `--document-font-meta`.

### Project roles

Project presentation provides its own semantic roles:

- `--project-font-title`;
- `--project-font-tagline`;
- `--project-font-cta`.

These roles may resolve to the same underlying font families as general site typography while remaining semantically distinct.

### Type scale (`--text-*`)

Current scale:

`sm` → `base` → `lg` → `xl` → `2xl` → `3xl` → `4xl`

Numeric values may evolve while the scale remains coherent.

Fluid or composition-specific sizes may remain local using mechanisms such as `clamp()` rather than requiring a new global token.

---

## Spacing (`--space-*`)

Consistent geometric rhythm.

Current scale:

`xs` → `sm` → `md` → `lg` → `xl` → `2xl` → `3xl`

Numeric values may shift; the scale remains consistent.

Local values are acceptable when no reusable spacing role has yet emerged.

---

## Layout

Global layout tokens currently include:

- `--content-width`;
- `--article-width`;
- `--site-header-height`;
- `--project-hero-height`.

Some layout tokens are responsively overridden in `tokens.css`.

Responsive variation of a token does not create a new semantic role: the token retains the same meaning while its value adapts to the viewport.

Component-specific layout values should remain local until reuse demonstrates that they belong in the global system.

---

## Radii (`--radius-*`)

The current radius scale is:

`xs` → `sm` → `md`

Radii should remain restrained. The visual language generally favors structural geometry over heavily rounded interface elements.

---

## Elevation (`--elevation-*`)

Visual hierarchy expressed through elevation.

| Token | Use Case |
| --- | --- |
| `--elevation-1` | Subtle separation |
| `--elevation-2` | Primary element within its local context |
| `--elevation-3` | Dominant element in the current composition |

Use sparingly. Flat layouts are the default.

---

## Image Treatments

### General filters

Reusable image treatments may be used when the source asset cannot reasonably be prepared beforehand.

| Token | Use Case |
| --- | --- |
| `--filter-cool` | Technical or industrial imagery |
| `--filter-warm` | Archival or historical content |

Keep treatments subtle. They are not a replacement for appropriate source imagery.

### Engineering-document imagery

The engineering-document presentation additionally defines:

- `--document-image-filter`;
- `--document-image-position`;
- `--document-thumbnail-ratio`.

These values provide consistent treatment for document imagery without forcing that presentation onto unrelated site content.

Component-specific image composition should remain local where appropriate.

For example, project hero image positioning currently uses the component-level `--project-image-position` variable rather than a global design token.

---

## Motion (`--ease-*`)

Interaction timing intent is currently represented by:

| Token | Use Case |
| --- | --- |
| `--ease-out` | Immediate interface feedback |
| `--ease-in-out` | More visible state transitions |

Despite the current `--ease-*` names, these values presently contain both **duration and timing function**.

For example, a token may represent a complete value such as:

`120ms ease-out`

Consumers therefore use these tokens as transition timing values rather than as easing curves alone.

This distinction must be preserved during any future namespace reconciliation.

---

## Framework Integration

The Flying Fortress Games design system must remain independent of Tailwind CSS.

`tokens.css` is the canonical design vocabulary.

Semantic CSS and Hugo templates consume that vocabulary directly.

Tailwind may expose or consume selected design values where doing so provides a concrete implementation benefit. Tailwind-specific integration must not silently redefine the meaning of an existing FFG token.

The current site does not depend on:

- a Tailwind `@theme` design-system layer;
- an `@apply` component architecture;
- widespread Tailwind utility composition in Hugo templates.

Introducing any of these remains optional and should be justified by demonstrated value.

Migration to Tailwind syntax is not itself an objective.

### Namespace compatibility

Some existing FFG token namespaces overlap with namespaces relevant to Tailwind integration.

Known areas requiring deliberate review include:

- `--text-*`;
- `--radius-*`;
- `--ease-*`.

These tokens must not be mechanically mapped or renamed.

Their existing semantics must first be compared with the semantics expected by the integration layer.

The `--ease-*` namespace deserves particular care because the existing FFG tokens contain complete transition timing values rather than easing curves alone.

Namespace reconciliation belongs to a separate implementation pass after this architecture has been documented.

---

## Abstraction Rules

1. **Semantic intent over implementation mechanism.**
2. **Semantic names over visual descriptions.**
3. **The FFG design system remains framework-neutral.**
4. **Components consume established tokens; they do not independently define the global design language.**
5. **Introduce new global tokens only when reuse or a stable semantic role has been demonstrated.**
6. **Component-specific and page-specific values remain local until a broader pattern naturally emerges.**
7. **Do not abstract merely to eliminate repetition.**
8. **Responsive value changes do not require new semantic tokens when the underlying role remains unchanged.**
9. **Consistency outweighs completeness.**
10. **Prefer evidence over anticipation. Abstract only after patterns have been validated in real components.**
11. **Framework integration must adapt to the design system, not redefine it.**
