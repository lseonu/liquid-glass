# Liquid Glass Quick Reference

Quick reference for the most common Liquid Glass patterns and tokens.

## Glass Effect (One-liner)

```css
background: rgba(255, 255, 255, 0.08);
backdrop-filter: blur(56px) saturate(200%) brightness(1.1);
border: 0.5px solid rgba(255, 255, 255, 0.18);
border-radius: 20px;
box-shadow: 0 4px 24px rgba(0, 0, 0, 0.06), inset 0 0.5px 0 rgba(255, 255, 255, 0.5);
```

## Essential Tokens

| Token | Value | Usage |
|-------|-------|-------|
| `--glass-bg` | `rgba(255, 255, 255, 0.08)` | Glass surface |
| `--glass-blur` | `56px` | Blur amount |
| `--glass-border` | `rgba(255, 255, 255, 0.18)` | Glass edge |
| `--glass-fill` | `rgba(255, 255, 255, 0.12)` | Elements inside glass |
| `--color-accent` | `#10B981` | Primary action color |

## Glass Fill (for nested elements)

```css
background: rgba(255, 255, 255, 0.12);
border: 1px solid rgba(255, 255, 255, 0.15);
```

## Input/Textarea Glass

```css
background: rgba(255, 255, 255, 0.12);
backdrop-filter: blur(48px) saturate(180%);
border: 1px solid rgba(255, 255, 255, 0.2);
border-radius: 20px;

&:focus-within {
  background: rgba(255, 255, 255, 0.2);
  border-color: rgba(255, 255, 255, 0.3);
}
```

## Send/Action Button

```css
background: #1D1D1F;
color: #fff;
border-radius: 50%;
width: 38px;
height: 38px;
```

## Primary Button

```css
background: var(--color-accent);
color: white;
border-radius: 20px;
padding: 10px 24px;
```

## Border Radius Scale

| Name | Value |
|------|-------|
| Small | `6px` |
| Medium | `10px` |
| Large | `14px` |
| XL | `20px` |
| Pill | `100px` |

## Transitions

```css
--transition-fast:   150ms cubic-bezier(0.23, 1, 0.32, 1);
--transition-base:   250ms cubic-bezier(0.23, 1, 0.32, 1);
--transition-slow:   400ms cubic-bezier(0.23, 1, 0.32, 1);
```

## Font Sizes

| Name | Value |
|------|-------|
| xs | `12px` |
| sm | `13px` |
| base | `14px` |
| md | `16px` |
| lg | `20px` |
| xl | `24px` |
| 2xl | `32px` |

## Shadows

```css
--shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.04);
--shadow-md: 0 2px 8px rgba(0, 0, 0, 0.06);
--shadow-lg: 0 4px 16px rgba(0, 0, 0, 0.08);
```

## Don't Do

- ❌ Glass inside glass → use fills
- ❌ Heavy borders
- ❌ Sharp corners
- ❌ Opaque surfaces
- ❌ Flat shadows

## See Also

- [Liquid Glass Design System](liquid-glass-design-system.md) ([[liquid-glass-design-system]]) — Full implementation guide with all tokens
- [General Design Guidelines](general-design-guidelines.md) ([[general-design-guidelines]]) — Core design principles
- [Color Palette](color-palette.md) ([[color-palette]]) — Complete color system
- [Spacing System](spacing-system.md) ([[spacing-system]]) — Spacing scale and layout conventions
- [Component Patterns](component-patterns.md) ([[component-patterns]]) — Ready-to-use code snippets
