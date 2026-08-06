# FFG Projects — Glass Navigation Tuning Pass

## Scope

This pass changes styling only:

- Zero HTML changes.
- Zero JavaScript changes.
- Existing keyboard navigation, mobile swiping and scroll snapping remain unchanged.

## Desktop layout

- The focused project occupies approximately 80% of the viewport.
- The previous and next projects remain visible in side panes of approximately 10% each.
- Neighbouring panes are blurred and dimmed so the current project is focused, but not isolated.

## Side rails

Each neighbouring pane has a sharp 7px inner rail, kept outside the blurred layer:

- 3px solid bronze facing the focused project.
- 4px using the neighbouring project’s `theme_color`.
- The coloured section uses a 25° gradient from the base tint toward a lighter version of that tint.
- Hover slightly reduces blur and dimming and gives the coloured section a restrained glow.

## Project indicators

- Retain one small Art Deco indicator per project.
- The active project remains visibly marked.
- Hover and keyboard focus use the project’s `theme_color`.
- The project dossier displays its corresponding small indicator.

## Mobile

- Do not display the narrow glass side panes.
- Retain the existing indicator navigation, swiping and scroll snapping.

## Deferred JavaScript enhancement

The following work is explicitly deferred to the next session:

- Clicking a blurred side pane to centre its project.
- Automatic active-state synchronisation across every navigation method.

