# base-ui-react

Skill for working with `@base-ui/react` in React applications. It helps not only with adding Base UI primitives, but also with making correct architectural decisions around them: component selection, composition, styling, forms, accessibility, and version-aware migrations.

## Install

Install command:

```bash
npx skills add aiko-atami/baseui-skills --skill base-ui-react
```

## What It Covers

- Adding and adopting Base UI in a screen, feature, or existing interface.
- Choosing the right primitive for a UX requirement.
- Composing Base UI parts into app-level components without breaking `ref`, prop spreading, or accessibility.
- Porting documentation examples into the project's styling stack: Tailwind, CSS Modules, CSS-in-JS, or plain CSS.
- Forms, validation, and integration with form libraries.
- Animations and transitions, including Motion-based scenarios.
- Version checks, compatibility constraints, and migration guidance.
- Reviewing Base UI code with focus on accessibility, state modeling, and behavioral regressions.

## Supported Task Types

The skill is explicitly organized around 8 task types:

- `adopt` - add Base UI to a new or existing part of the app.
- `choose` - select the correct component for a given scenario.
- `compose` - build app-level UI abstractions on top of Base UI.
- `style` - port examples from the docs into the project's styling stack.
- `forms` - wire `Field`, `Fieldset`, `Form`, hidden inputs, and validation behavior.
- `motion` - implement transitions, animations, and Motion-based behavior.
- `migrate` - reconcile code with release notes and installed-version constraints.
- `review` - inspect implementations for mistakes and anti-patterns.

## Covered Components

The skill covers the main Base UI component families:

- Overlays and popups: `Alert Dialog`, `Dialog`, `Drawer`, `Popover`, `Tooltip`, `Preview Card`, `Toast`.
- Menus and navigation: `Menu`, `Context Menu`, `Menubar`, `Navigation Menu`, `Toolbar`.
- Form foundations: `Button`, `Field`, `Fieldset`, `Form`, `Input`.
- Choice and value inputs: `Autocomplete`, `Calendar`, `Checkbox`, `Checkbox Group`, `Combobox`, `Number Field`, `Radio`, `Select`, `Slider`, `Switch`.
- Disclosure, layout, status, and display: `Accordion`, `Collapsible`, `Tabs`, `Scroll Area`, `Separator`, `Avatar`, `Meter`, `Progress`, `Toggle`, `Toggle Group`.
- Utilities: `CSPProvider`, `DirectionProvider`, `mergeProps`, `useRender`.

## Covered Integration Topics

- Accessibility: accessible names, focus management, keyboard interaction, and correct use of tooltips and popup components.
- Forms: native submit, `onFormSubmit`, hidden inputs, browser validation, custom validation, and `Field`-based composition.
- Styling: state-based `className`/`style`, documented `data-*` attributes, CSS variables, and porting examples into different styling stacks.
- Composition API: `render`, `mergeProps`, `useRender`, and nested composition of multiple primitives on a single trigger.
- State model: uncontrolled by default, with controlled pairs such as `open/onOpenChange` and `value/onValueChange`.
- Event model: `eventDetails`, change reasons, cancelable state changes, and propagation control.
- Detached triggers and multi-trigger scenarios via `createHandle()`.
- CSP and RTL: `CSPProvider`, `DirectionProvider`, and correct behavior across portals.
- Tailwind CSS v3 compatibility when official examples target Tailwind CSS v4.

## Reference Base

The skill is built around these reference files:

- `references/index.md` - documentation map and entry point.
- `references/component-catalog.md` - component catalog and selection guidance.
- `references/integration-playbook.md` - setup, accessibility, styling, forms, composition, and TypeScript guidance.
- `references/patterns-and-apis.md` - common part trees, state and event patterns, animation, `mergeProps`, and `useRender`.
- `references/tailwind-v3-compat.md` - guidance for porting examples into Tailwind CSS v3.
- `references/releases.md` - version gating and practical migration notes.

## Default Assumptions

- Choose component semantics before visual styling.
- Prefer composable Base UI parts over opaque app-specific abstractions.
- Prefer uncontrolled state unless external orchestration is required.
- Prefer `Field` for form controls instead of rebuilding labels, errors, and descriptions by hand.
- Prefer documented `data-*` attributes and CSS variables over fragile DOM selectors.
- Prefer `Dialog` over `Drawer` when swipe gestures and snap points are not needed.
- Prefer `Combobox` over `Select` for large filterable datasets.
- Prefer `Autocomplete` when free-form input is valid.

## Boundaries And Guardrails

- Do not use `Tooltip` as the only label or the only place for important information.
- Do not copy Tailwind v4 examples directly into a Tailwind v3 project.
- Do not forget `Portal` in popup component trees.
- Do not confuse action menus with navigation primitives.
- Do not break `ref` forwarding or prop spreading when composing through `render`.
- Do not use features that are unavailable in the installed `@base-ui/react` version.
