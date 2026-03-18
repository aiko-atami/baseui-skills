# Base UI Component Catalog

## Contents

- Overlays and popups
- Menus and navigation
- Form foundations
- Choice and value inputs
- Disclosure, layout, status, and display
- Utilities

## Overlays and Popups

- `Alert Dialog`
  Use for destructive, blocking, or safety-critical confirmation flows that require a user response. Docs: `https://base-ui.com/react/components/alert-dialog`
- `Dialog`
  Use for general-purpose modal flows and forms that open above the page. If a side sheet does not need gestures, it is still a positioned dialog. Docs: `https://base-ui.com/react/components/dialog`
- `Drawer`
  Use for edge sheets that need swipe gestures, snap points, or indent effects. Prefer `Dialog` when those behaviors are not needed. Docs: `https://base-ui.com/react/components/drawer`
- `Popover`
  Use for anchored contextual content, optionally hover-open or modal. Prefer it over Tooltip when the popup itself is the interaction target or the content matters for accessibility. Docs: `https://base-ui.com/react/components/popover`
- `Tooltip`
  Use for visual-only hints for sighted mouse and keyboard users. Never use it as the only label or the only place for important information. Docs: `https://base-ui.com/react/components/tooltip`
- `Preview Card`
  Use for hover or focus previews of linked content. The trigger is a link by default and the component is best for sighted previews, not essential content. Docs: `https://base-ui.com/react/components/preview-card`
- `Toast`
  Use for transient notifications, announced feedback, or contextual feedback messages that should be screen-reader friendly. Docs: `https://base-ui.com/react/components/toast`

## Menus and Navigation

- `Menu`
  Use for dropdown lists of actions. It supports submenus, checkbox and radio items, detached triggers, and `LinkItem` for semantic navigation links in newer versions. Docs: `https://base-ui.com/react/components/menu`
- `Context Menu`
  Use for right-click or long-press contextual actions that appear at the pointer. Docs: `https://base-ui.com/react/components/context-menu`
- `Menubar`
  Use for desktop-style application command bars with top-level menus. Docs: `https://base-ui.com/react/components/menubar`
- `Navigation Menu`
  Use for site navigation made of links and nested menus. Do not substitute it for an action menu. Docs: `https://base-ui.com/react/components/navigation-menu`
- `Toolbar`
  Use for compact groups of controls with roving focus. In horizontal toolbars, keep inputs rare, use at most one, and place it last. Docs: `https://base-ui.com/react/components/toolbar`

## Form Foundations

- `Button`
  Use for generic actions when no richer input or popup primitive is needed. It can render as another tag and remain focusable when disabled. Docs: `https://base-ui.com/react/components/button`
- `Field`
  Use to add a label, description, validation, error message, and state hooks around a single control. This is the default wrapper for most Base UI form controls. Docs: `https://base-ui.com/react/components/field`
- `Fieldset`
  Use to group related controls under a stylable legend, especially for checkbox or radio groups. Docs: `https://base-ui.com/react/components/fieldset`
- `Form`
  Use for native submission, `onFormSubmit` object payloads, and consolidated error handling. Docs: `https://base-ui.com/react/components/form`
- `Input`
  Use for plain text-style inputs when you do not need richer composite behavior such as Select, Combobox, or Number Field. Docs: `https://base-ui.com/react/components/input`

## Choice and Value Inputs

- `Select`
  Use for short, predefined lists when filtering is not necessary. It behaves like a listbox-style picker and aligns the selected item text with the trigger by default. Docs: `https://base-ui.com/react/components/select`
- `Combobox`
  Use for large predefined data sets that should be filterable but still constrain the final value to listed items. Do not use it for free-form search. Docs: `https://base-ui.com/react/components/combobox`
- `Autocomplete`
  Use for free-form input with suggestions, inline completion, search widgets, or command palettes. Do not use it when the selected option must remain canonical like a select value. Docs: `https://base-ui.com/react/components/autocomplete`
- `Checkbox`
  Use for boolean or multi-select form choices. Prefer an enclosing label or `Field` for labeling. Docs: `https://base-ui.com/react/components/checkbox`
- `Checkbox Group`
  Use when multiple checkbox values should share state and submit as a single field. Docs: `https://base-ui.com/react/components/checkbox-group`
- `Radio`
  Use with `RadioGroup` when exactly one option must be selected from a defined set. Docs: `https://base-ui.com/react/components/radio`
- `Switch`
  Use for on or off settings. Prefer it over Checkbox when the control represents a setting rather than a selection list. Docs: `https://base-ui.com/react/components/switch`
- `Number Field`
  Use for numeric entry with increment and decrement controls, parsing, validation, or scrub interactions. Docs: `https://base-ui.com/react/components/number-field`
- `Slider`
  Use for scrub, range, and percentage-like interactions driven by dragging rather than direct typing. Docs: `https://base-ui.com/react/components/slider`
- `Calendar`
  Use for visual date picking or month-based date navigation. Docs: `https://base-ui.com/react/components/calendar`

## Disclosure, Layout, Status, and Display

- `Accordion`
  Use for multiple collapsible sections with headings, such as FAQs or settings groups. Docs: `https://base-ui.com/react/components/accordion`
- `Collapsible`
  Use for a single show or hide region controlled by a button. Docs: `https://base-ui.com/react/components/collapsible`
- `Tabs`
  Use for a single active panel among several related content sections on the same page. Docs: `https://base-ui.com/react/components/tabs`
- `Scroll Area`
  Use for native scrolling with custom scrollbars inside constrained panes, dialogs, or popups. Docs: `https://base-ui.com/react/components/scroll-area`
- `Separator`
  Use for semantic dividers that assistive technologies should understand. Docs: `https://base-ui.com/react/components/separator`
- `Avatar`
  Use for user or entity avatars with fallback handling. Docs: `https://base-ui.com/react/components/avatar`
- `Meter`
  Use for static measured values within a known range, such as score, level, or capacity. Docs: `https://base-ui.com/react/components/meter`
- `Progress`
  Use for work completion or loading progress that changes over time. Docs: `https://base-ui.com/react/components/progress`
- `Toggle`
  Use for a single two-state button where button semantics are more appropriate than checkbox or switch semantics. Docs: `https://base-ui.com/react/components/toggle`
- `Toggle Group`
  Use for coordinated toggle buttons such as segmented controls, alignment pickers, or multi-press button groups. Docs: `https://base-ui.com/react/components/toggle-group`

## Utilities

- `CSPProvider`
  Use when strict CSP requires a nonce on inline Base UI styles or scripts, or when inline styles must be disabled. Docs: `https://base-ui.com/react/utils/csp-provider`
- `DirectionProvider`
  Use when Base UI components must behave correctly in RTL layouts, especially when portals would otherwise lose directional context. Docs: `https://base-ui.com/react/utils/direction-provider`
- `mergeProps`
  Use when composing several prop sources into one rendered part without losing event handlers, classes, or style objects. Docs: `https://base-ui.com/react/utils/merge-props`
- `useRender`
  Use when building your own primitive that should expose a Base UI-style `render` prop and preserve composition semantics. Docs: `https://base-ui.com/react/utils/use-render`
