---
name: base-ui-react
description: Implement, refactor, review, or explain `@base-ui/react` in React applications. Use when working with Base UI components or utilities.
---

# Base UI React

Base UI `v1.3.0`, released on March 12, 2026.

## Workflow

1. Classify the task:
- `adopt`: add Base UI to a screen or feature.
- `choose`: pick the right primitive for a UX requirement.
- `compose`: wrap Base UI parts in app-level components.
- `style`: port docs examples into the project styling stack.
- `forms`: wire `Field`, `Fieldset`, `Form`, validation, or form libraries.
- `motion`: add transitions or Motion-based animations.
- `migrate`: reconcile code with release notes or newer docs.
- `review`: inspect Base UI code for accessibility, state, or regression issues.

2. Load only the references you need:
- Always start with `references/index.md`.
- Load `references/component-catalog.md` when selecting a component or learning an unfamiliar one.
- Load `references/integration-playbook.md` for setup, accessibility, styling, forms, and TypeScript guidance.
- Load `references/patterns-and-apis.md` for common anatomy, controlled state, detached triggers, event details, and utility behavior.
- Load `references/tailwind-v3-compat.md` whenever the target project uses Tailwind CSS v3.
- Load `references/releases.md` when the installed version may lag behind the docs or when migrations matter.

3. Check local constraints before editing:
- Inspect `package.json` for the installed `@base-ui/react` version.
- Inspect the styling stack before copying examples.
- If Tailwind is present, determine whether the project is on v3 or v4 first.
- For popup-heavy layouts, ensure the app root creates an isolated stacking context.
- For CSP or RTL requirements, load the relevant utility guidance before coding.

4. Build in the right order:
- Choose semantics before appearance.
- Start from the documented part anatomy, then layer styling and composition on top.
- Prefer uncontrolled defaults unless external orchestration requires controlled state.
- Prefer `Field` around Base UI form controls instead of recreating labels, descriptions, and errors by hand.
- Prefer `render`, `mergeProps`, and `useRender` over ad hoc wrapper patterns.
- Prefer documented data attributes and CSS variables over fragile DOM selectors.

5. Validate the behavior after implementation:
- Check accessible names for every trigger and form control.
- Check focus entry, focus return, keyboard navigation, and close behavior for overlays.
- Check hidden-input submission and validation bubbles for composite form controls.
- Check Tailwind v3 ports by rendered behavior, not by class-name similarity alone.
- If behavior differs from the docs, compare it against the installed package version before assuming a library bug.

## Defaults

- Prefer composable Base UI parts over opaque app-specific abstractions.
- Prefer CSS transitions over CSS animations for enter and exit work.
- Prefer `Dialog` over `Drawer` unless gestures, snap points, or sheet behavior are required.
- Prefer `Combobox` over `Select` for large filterable data sets.
- Prefer `Autocomplete` over `Combobox` when free-form input is valid.
- Prefer `Popover` over `Tooltip` when the popup content itself matters to the interaction.

## Guardrails

- Do not use Tooltip as the only accessible label or the only place for critical information.
- Do not copy official Tailwind CSS v4 examples verbatim into a Tailwind CSS v3 project.
- Do not forget `Portal` when assembling popup families.
- Do not replace action menus with site-navigation primitives or vice versa.
- Do not break `ref` forwarding or prop spreading when composing via `render`.
- Do not skip version checks when using docs features introduced after `v1.0.0`, such as `Drawer`, `CSPProvider`, `Select.Label`, `Combobox.InputGroup`, or `Tooltip`'s `closeOnClick`.
