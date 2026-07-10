# Design Tokens — Abstraction Rules

Tokens capture **semantic intent**, not implementation. Values evolve; usages remain stable.

---

## Elevation (`--elevation-*`)

Visual hierarchy expressed through elevation.

| Token         | Use Case                                    |
| ------------- | ------------------------------------------- |
| `elevation-1` | Subtle separation                           |
| `elevation-2` | Primary element within its local context    |
| `elevation-3` | Dominant element in the current composition |

Use sparingly. Flat layouts are the default.

---

## Borders (`--border-*`)

Structural and interaction boundaries.

| Token                | Use Case                                 |
| -------------------- | ---------------------------------------- |
| `border-base`        | Passive separators                       |
| `border-interactive` | Clickable or actionable elements         |
| `border-highlight`   | Emphasized states (hover, focus, active) |

> Note: `border-highlight` builds upon `border-interactive` for interactive elements.

Token names reflect purpose, not color.

---

## Filters (`--filter-*`)

Reusable image treatments when the source asset cannot reasonably be prepared beforehand.

| Token         | Use Case                        |
| ------------- | ------------------------------- |
| `filter-cool` | Technical or industrial imagery |
| `filter-warm` | Archival or historical content  |

Keep subtle. Not a replacement for proper image preparation.

---

## Spacing (`--space-*`)

Consistent geometric rhythm.

Scale: `xs` → `sm` → `md` → `lg` → `xl` → `2xl` → `3xl`

Numeric values may shift; the scale remains consistent.

---

## Typography (`--font-*`, `--text-*`)

Editorial function, not typefaces.

Roles: `--font-heading`, `--font-body`, `--font-mono`
Sizes: `--text-xs` → `--text-xl`

Changes to typography update tokens; components remain untouched.

---

## Colors (`--surface-*`, `--text-*`, `--accent-*`, `--border-*`)

Semantic roles over appearance.

| Category | Examples                                 |
| -------- | ---------------------------------------- |
| Surfaces | `--surface-page`, `--surface-panel`      |
| Text     | `--text-main`, `--text-muted`            |
| Accent   | `--accent-primary`, `--accent-secondary` |
| Borders  | `--border-base`, `--border-interactive`  |

Avoid appearance-based names such as `--blue`, `--gold`, or `--dark-gray`.

---

## Transitions (`--ease-*`)

Interaction timing intent.

| Token         | Use Case                     |
| ------------- | ---------------------------- |
| `ease-out`    | Immediate interface feedback |
| `ease-in-out` | Visible state transitions    |

Durations and timing curves belong to the token values.

---

## Principles

1. **Semantic names over visual descriptions.**
2. **Components consume tokens; they do not define design language.**
3. **Introduce new tokens only when reuse is demonstrated.**
4. **Page-specific values remain local until they naturally emerge elsewhere.**
5. **Consistency outweighs completeness.**
6. **Prefer evidence over anticipation. Abstract only after patterns have been validated in real components.**
