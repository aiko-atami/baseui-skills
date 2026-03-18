# Base UI Docs Map

- Official AI index: `https://base-ui.com/llms.txt`
- Tailwind note: official examples target Tailwind CSS v4. Load `tailwind-v3-compat.md` before porting them into a Tailwind CSS v3 codebase.

## Overview Pages

- Quick start: `https://base-ui.com/react/overview/quick-start`
  Install `@base-ui/react`, note that the package is tree-shakable, and add `.root { isolation: isolate; }` so portaled popups stay above page content.
- Accessibility: `https://base-ui.com/react/overview/accessibility`
  Use this to validate accessible naming, focus management, keyboard support, contrast, and testing expectations.
- About Base UI: `https://base-ui.com/react/overview/about`
  Use this for positioning Base UI as a headless, accessibility-first, styling-agnostic React library.
- Releases: `https://base-ui.com/react/overview/releases`
  Use this to confirm feature availability, breaking changes, and migration constraints.

## Handbook Pages

- Styling: `https://base-ui.com/react/handbook/styling`
  Load when mapping docs examples into Tailwind, CSS Modules, CSS-in-JS, or plain CSS.
- Animation: `https://base-ui.com/react/handbook/animation`
  Load when implementing transitions, CSS animations, or Motion-driven enter and exit behavior.
- Composition: `https://base-ui.com/react/handbook/composition`
  Load when using the `render` prop, custom components, or nested trigger composition.
- Customization: `https://base-ui.com/react/handbook/customization`
  Load when controlling state, reacting to `eventDetails`, or preventing default Base UI behavior.
- Forms: `https://base-ui.com/react/handbook/forms`
  Load for hidden inputs, native validation, `Field`, `Form`, and third-party form-library integration.
- TypeScript: `https://base-ui.com/react/handbook/typescript`
  Load for `Props`, `State`, event types, and `useRender` typing patterns.

## Component Families

- Load `component-catalog.md` for the per-component index and selection guidance.
- Disclosure and layout:
  `Accordion`, `Collapsible`, `Tabs`, `Scroll Area`, `Separator`
- Overlays and popups:
  `Alert Dialog`, `Dialog`, `Drawer`, `Popover`, `Tooltip`, `Preview Card`, `Toast`
- Menus and navigation:
  `Menu`, `Context Menu`, `Menubar`, `Navigation Menu`, `Toolbar`
- Form foundations:
  `Button`, `Field`, `Fieldset`, `Form`, `Input`
- Choice and value inputs:
  `Autocomplete`, `Calendar`, `Checkbox`, `Checkbox Group`, `Combobox`, `Number Field`, `Radio`, `Select`, `Slider`, `Switch`
- Status and media:
  `Avatar`, `Meter`, `Progress`, `Toggle`, `Toggle Group`

## Utilities

- CSP Provider: `https://base-ui.com/react/utils/csp-provider`
  Load when inline styles or scripts need a CSP nonce or must be disabled.
- Direction Provider: `https://base-ui.com/react/utils/direction-provider`
  Load when components must behave correctly in RTL contexts, especially across portals.
- mergeProps: `https://base-ui.com/react/utils/merge-props`
  Load when composing Base UI parts or implementing a custom `render` callback.
- useRender: `https://base-ui.com/react/utils/use-render`
  Load when building app-level primitives that should expose a Base UI-style `render` prop.
