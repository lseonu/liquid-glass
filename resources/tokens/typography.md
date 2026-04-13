# Typography Tokens

Typography system for Santai's Liquid Glass UI.

## Font Stack

```css
font-family: 
  -apple-system, 
  BlinkMacSystemFont, 
  'SF Pro Display', 
  'SF Pro Text', 
  'Segoe UI', 
  Roboto, 
  'Helvetica Neue', 
  Helvetica, 
  Arial, 
  sans-serif;
```

## Font Sizes

| Token | Value | Pixels |
|-------|-------|--------|
| `--font-size-xs` | `0.75rem` | 12px |
| `--font-size-sm` | `0.8125rem` | 13px |
| `--font-size-base` | `0.875rem` | 14px |
| `--font-size-md` | `1rem` | 16px |
| `--font-size-lg` | `1.25rem` | 20px |
| `--font-size-xl` | `1.5rem` | 24px |
| `--font-size-2xl` | `2rem` | 32px |

## Font Weights

- Use regular (400) and medium (500) weights
- Avoid thin or heavy weights
- Letter spacing: slight positive tracking for headings

## Line Heights

| Token | Value | Usage |
|-------|-------|-------|
| `--line-height-tight` | `1.25` | Headings |
| `--line-height-normal` | `1.5` | Body text |
| `--line-height-relaxed` | `1.75` | Long-form content |

## Letter Spacing

| Token | Value | Usage |
|-------|-------|-------|
| `--tracking-tight` | `-0.01em` | Large headings |
| `--tracking-normal` | `0` | Body text |
| `--tracking-wide` | `0.02em` | Small caps, labels |

## Icon Style

- Use **stroke-based icons** with `stroke-width: 1.5` for SF Symbols aesthetic
- Icons should be clean, geometric, and consistent in weight
- Size: 20px for standard, 24px for larger

---

## See Also

- [Spacing Tokens](./spacing.md) — Spacing scale and layout
- [Color Tokens](./colors.md) — Text color system
- [Design Principles](../principles/) — Typography guidelines
