# Tailwind CSS v3 Compatibility for Base UI Examples

- Official Base UI Tailwind examples target Tailwind CSS v4.
- If the target project uses `tailwindcss@3.x`, convert v4-only syntax before copying examples.
- If an exact v3 utility does not exist, preserve the visual behavior with CSS Modules or plain CSS instead of inventing unsupported utilities.

## High-Confidence Conversions

| Tailwind v4 pattern | Tailwind v3-compatible approach |
| --- | --- |
| `@import "tailwindcss";` | Use `@tailwind base;`, `@tailwind components;`, and `@tailwind utilities;` in the global stylesheet. |
| `@utility foo { ... }` | Define the class inside `@layer utilities { .foo { ... } }`. |
| `@theme { ... }` variables | Move values into `tailwind.config.*` `theme.extend` or regular CSS variables. |
| `shadow-xs` | Use `shadow-sm`. |
| `rounded-xs` | Use `rounded-sm`. |
| `blur-xs` | Use `blur-sm`. |
| `outline-hidden` | Use `outline-none`. |
| `bg-linear-to-r` | Use `bg-gradient-to-r`. |
| `bg-linear-to-l` | Use `bg-gradient-to-l`. |
| `bg-linear-to-t` | Use `bg-gradient-to-t`. |
| `bg-linear-to-b` | Use `bg-gradient-to-b`. |
| `bg-(--token)` or `text-(--token)` | Use arbitrary values like `bg-[var(--token)]` or `text-[var(--token)]`. |
| `hover:bg-red-500!` | Move the important modifier to the front as `hover:!bg-red-500`. |
| Order-sensitive variant stacking such as `*:first:pt-0` | Reverse to the v3 order, for example `first:*:pt-0`. |

## Safe Porting Rules

- Set `ring-*`, `ring-color`, `border`, and `border-color` explicitly instead of relying on version-specific defaults.
- Keep gradients explicit with `from-*`, `via-*`, and `to-*` classes instead of relying on newer shorthand behavior.
- If a docs example depends on a v4-only feature and the v3 translation becomes awkward, move the styling into a CSS module and keep Base UI structure intact.
- Prefer simple, explicit utility sets over trying to preserve every v4 shorthand exactly.

## When to Stop Converting and Use CSS

- Stop translating utility-for-utility when:
  the example depends on new directives, new theme-variable syntax, or variant ordering that obscures intent.
- Move the styling to CSS when:
  the semantic structure matters more than the utility spelling.
- Keep the Base UI part tree unchanged even if the styling mechanism changes.
