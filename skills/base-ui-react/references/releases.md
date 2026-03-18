# Base UI Release Notes for Practical Migrations

## Current Baseline

- Official releases page marks `v1.3.0` as the latest stable release on March 12, 2026.
- If the local project is older, gate any newer props or parts before using them.

## Stable Releases That Matter Most

- `v1.3.0` on March 12, 2026
  `Drawer` became stable, `Menu` gained content transitions with `Viewport`, `Select`, `Combobox`, and `Slider` gained `Label` parts, `Drawer` gained `SwipeArea`, `Combobox` and `Autocomplete` gained `InputGroup`, and `Tooltip` gained `closeOnClick`.
- `v1.2.0` on February 12, 2026
  Added preview `Drawer`, `useFilteredItems` for `Autocomplete` and `Combobox`, lazy elements in `render`, `keepMounted` on `NavigationMenu`, and `finalFocus` on `Select`.
- `v1.1.0` on January 15, 2026
  Added `loopFocus` for `Autocomplete` and `Combobox`, placeholder props for `Combobox` and `Select`, `CSPProvider`, and multiple popup and form fixes.
- `v1.0.0` on December 11, 2025
  Marked the first stable `@base-ui/react` release and the new docs site, with 35 unstyled components plus broad focus and form fixes.

## Pre-1.0 and Early Migration Notes

- `v1.0.0-rc.0`
  `Checkbox` and `Switch` moved closer to native unchecked submission behavior, `Tabs.Panel` `keepMounted` behavior changed, `Combobox` dropped `keepHighlight`, `Menu` and `Select` gained `highlightItemOnHover`, and popup closing behavior changed in `Dialog` and `Popover`.
- `v1.0.0-beta.5`
  Added `Button`, detached triggers across popup families, and major `Autocomplete` and `Combobox` improvements. Release summaries also call out beta-era renames such as `loop` to `loopFocus`.
- `v1.0.0-beta.4` and `v1.0.0-beta.3`
  Standardized event-details APIs, added `Autocomplete` and `Combobox`, improved `Select`, and expanded `initialFocus` and `finalFocus`.
- `v1.0.0-alpha.5`
  Made `Portal` a required part for popup components. If very old examples omit it, update them.

## Version-Gated Features to Watch

- If the project is below `v1.3.0`, do not assume `Drawer.SwipeArea`, `Combobox.InputGroup`, `Autocomplete.InputGroup`, `Menu.Viewport` content transitions, `Tooltip.closeOnClick`, or `Label` parts on `Select`, `Combobox`, and `Slider` exist.
- If the project is below `v1.2.0`, do not assume `Select.finalFocus` or `NavigationMenu` `keepMounted` exist.
- If the project is below `v1.1.0`, do not assume `CSPProvider`, `loopFocus`, or placeholder props on `Combobox` and `Select` exist.

## Canary Releases

- Base UI publishes canary builds through `https://pkg.pr.new/@base-ui/react@...`.
- Use canaries only when the task explicitly calls for trying unreleased fixes or behavior.
