# Base UI Patterns and APIs

## Common Anatomy Patterns

- Modal popup pattern:
  `Root -> Trigger -> Portal -> Backdrop -> Viewport -> Popup -> Title/Description/Close`
- Anchored popup pattern:
  `Root -> Trigger -> Portal -> Backdrop? -> Positioner -> Popup -> Arrow?`
- List and picker pattern:
  `Root -> Trigger or Input -> Portal -> Positioner -> Popup -> List -> Item`
- Form-wrapper pattern:
  `Field.Root -> Field.Label -> control -> Field.Error -> Field.Description`

## State Model

- Base UI components are uncontrolled by default.
- Make them controlled with pairs such as `open` and `onOpenChange`, `value` and `onValueChange`, or `pressed` and `onPressedChange`.
- Prefer reacting inside `onOpenChange` or `onValueChange` over adding effects that watch the same state later.
- Many change handlers receive `eventDetails` as a second argument. Use it when behavior depends on why the state changed.

## Base UI Event Details

- `eventDetails.reason` explains why the change happened.
- `eventDetails.event` exposes the originating DOM event when present.
- `eventDetails.cancel()` blocks the state change when the component supports cancellation.
- `eventDetails.allowPropagation()` lets the originating DOM event bubble when Base UI would otherwise stop it.
- `preventBaseUIHandler()` on a React synthetic event stops Base UI's internal handler without calling `preventDefault()` or `stopPropagation()`.

## Detached Triggers and Multiple Triggers

- Popup families such as `Dialog`, `AlertDialog`, `Popover`, `Tooltip`, and `PreviewCard` support detached triggers via `createHandle()`.
- Reuse the same handle for multiple triggers when one popup can be opened from several places.
- Use trigger `payload` plus a render-function child on the root when popup content depends on which trigger opened it.
- In controlled multi-trigger setups, manage `triggerId` in addition to `open`.

## Styling Hooks

- Use `className={(state) => ...}` and `style={(state) => ...}` when styles depend on internal state.
- Use documented `data-*` attributes such as `data-open`, `data-closed`, `data-highlighted`, `data-checked`, `data-invalid`, and animation-specific attributes.
- Use documented CSS variables such as popup sizing, transform-origin, and anchor dimensions instead of hard-coding measurements.

## mergeProps

- Treat `mergeProps` like `Object.assign` with smarter handling for React props.
- The rightmost prop object wins for normal keys.
- `className` values concatenate with the rightmost value first.
- `style` objects merge with later keys overwriting earlier ones.
- Event handlers merge and run rightmost first.
- Refs do not merge automatically; the rightmost ref wins.
- If you use the function form, remember that its return value replaces the accumulated props unless you manually call prior handlers.

## useRender

- Use `useRender` to expose a `render` prop from your own primitives.
- Pass `defaultTagName`, `render`, and merged props into the hook.
- Merge internal and external props with `mergeProps` before passing them to `useRender`.
- Pass one ref or an array of refs through the `ref` option when both internal and external code need the DOM node.

## Animation

- Prefer CSS transitions with `[data-starting-style]` and `[data-ending-style]`.
- Use `[data-open]` and `[data-closed]` when CSS animations are a better fit.
- When using Motion with popup parts that unmount, control `open`, wrap the portal in `AnimatePresence`, and use `keepMounted` where the docs require it.
- Animate `opacity` as part of Motion transitions so Base UI can detect completion through `element.getAnimations()`. If the real effect is translational, a near-opaque value such as `0.9999` is still useful.
- Use `actionsRef.current.unmount()` when you need manual control over the final unmount timing.

## Special Cases

- Nested dialogs omit child backdrops and expose nested styling hooks such as `[data-nested-dialog-open]` and `--nested-dialogs`.
- `Tooltip.Provider` shares open and close delays across adjacent tooltips.
- `Popover`, `PreviewCard`, and newer `Menu` patterns can animate content changes with `Viewport` and `data-activation-direction`.
