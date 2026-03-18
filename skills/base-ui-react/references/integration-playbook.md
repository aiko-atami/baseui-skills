# Base UI Integration Playbook

## Setup

- Install `@base-ui/react` and import components from documented subpaths such as `@base-ui/react/dialog`.
- Treat examples as compositional skeletons, not as mandatory styling choices.
- For any screen with portaled popups, ensure the application layout root creates a stacking context:
  `.root { isolation: isolate; }`

## Accessibility

- Give every trigger and every form control an accessible name.
- Use Tooltip only as a supplementary visual label for sighted mouse and keyboard users.
- Keep important descriptions inline or move them into Popover or another accessible surface.
- Use `Field`, `Fieldset`, or explicit group labeling for checkbox groups and radio groups.
- Preserve visible focus treatments after styling. Base UI handles focus logic, but not your color choices.

## Forms

- Wrap Base UI controls in `Field.Root name="..."` when they should participate in form submission.
- Remember that composite controls use hidden inputs for form submission and validation.
- When the control is popup-based, keep the control inside a relatively positioned wrapper so the browser validation bubble anchors near the visible control.
- Use native `onSubmit` when you want `FormData`.
- Use `onFormSubmit` when you want a JavaScript object payload and automatic `preventDefault()`.
- Use `validate`, `validationMode`, and `validationDebounceTime` for custom validation.
- Use `Field.Error` without children for the default native error message, or with `match` for custom messages.
- When labeling button-like controls such as `Select.Trigger` or `Combobox.Trigger`, follow the docs pattern with `Field.Label nativeLabel={false}` when needed to avoid native label quirks.
- Integrate React Hook Form or TanStack Form by externally controlling state when the app already has a form-state owner.

## Styling

- Use `className` and `style` directly on every rendered part.
- Use function forms of `className` and `style` when styles depend on component state.
- Prefer documented data attributes and CSS variables over custom DOM traversal.
- Use Tailwind, CSS Modules, CSS-in-JS, or plain CSS based on the host project.
- If the target repo is on Tailwind CSS v3, load `tailwind-v3-compat.md` before copying any official example.

## Composition

- Use the `render` prop to swap tags or compose Base UI parts with app components.
- Make custom rendered components forward the `ref` and spread the received props onto the underlying DOM node.
- Nest `render` props when composing multiple primitives around one trigger, such as `Tooltip` plus `Dialog` plus `Menu`.

## TypeScript

- Use `Component.Part.Props` when creating wrappers around documented parts.
- Use `Component.Part.State` when state-driven styling or custom `render` logic needs strong typing.
- Use `Component.Part.ChangeEventDetails` and `ChangeEventReason` when handling Base UI change callbacks.
- Use `useRender.ComponentProps` for public wrapper props and `useRender.ElementProps` for internal default props.
- In React 19, a primitive can often read `props.ref` directly. In React 18 and 17, use `React.forwardRef` when exposing a ref from custom wrappers.

## CSP and RTL

- Wrap relevant subtrees in `CSPProvider` when strict CSP requires a nonce for inline Base UI styles or scripts.
- Wrap relevant subtrees in `DirectionProvider` when components must behave correctly in RTL layouts.
- Remember that `DirectionProvider` affects Base UI behavior only. The app still needs `dir="rtl"` or `direction: rtl` in HTML or CSS.
