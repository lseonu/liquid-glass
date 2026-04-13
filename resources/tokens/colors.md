# Color Tokens

Color system for Santai's Liquid Glass UI.

## Base Colors

### Background

| Token | Hex | Usage |
|-------|-----|-------|
| `--color-bg` | `#F5F5F7` | Page background |
| `--color-surface` | `#FFFFFF` | Cards, panels |
| `--color-sidebar` | `#FBFBFD` | Sidebar background |

### Text

| Token | Hex | Usage |
|-------|-----|-------|
| `--color-text-primary` | `#1D1D1F` | Headings, body |
| `--color-text-secondary` | `#86868B` | Muted text |
| `--color-text-tertiary` | `#AEAEB2` | Placeholders |

### Accent

| Token | Hex | Usage |
|-------|-----|-------|
| `--color-accent` | `#10B981` | Primary action (grass green) |
| `--color-accent-hover` | `#059669` | Hover state |

### Borders

| Token | Hex | Usage |
|-------|-----|-------|
| `--color-border` | `#E5E5EA` | Dividers |
| `--color-border-light` | `#EFEFEF` | Subtle borders |

### Sidebar States

| Token | Hex | Usage |
|-------|-----|-------|
| `--color-sidebar` | `#FBFBFD` | Default |
| `--color-sidebar-hover` | `#F0F0F5` | Hover |
| `--color-sidebar-active` | `#E8E8F0` | Active |

---

## Glass Colors

### Glass Backgrounds

```css
--glass-bg:           rgba(255, 255, 255, 0.08);   /* Default glass */
--glass-bg-hover:     rgba(255, 255, 255, 0.12);   /* Hover state */
--glass-bg-active:    rgba(255, 255, 255, 0.18);   /* Active/pressed */
--glass-bg-pressed:   rgba(255, 255, 255, 0.05);   /* Pressed state */
```

### Glass Highlights

```css
--glass-highlight:      rgba(255, 255, 255, 0.5);   /* Bright highlight */
--glass-highlight-soft: rgba(255, 255, 255, 0.25); /* Soft highlight */
--glass-border:         rgba(255, 255, 255, 0.18);  /* Glass edge */
```

### Glass Fills (for nested elements)

```css
--glass-fill:           rgba(255, 255, 255, 0.12);  /* Default fill */
--glass-fill-hover:     rgba(255, 255, 255, 0.20);  /* Hover fill */
--glass-fill-active:    rgba(255, 255, 255, 0.28);  /* Active fill */
```

### Dark Tint Fill

For contrast distinction in dark mode or overlays:
```css
background: rgba(0, 0, 0, 0.015);
```

### Overlay Colors

```css
/* Modal overlay */
background: rgba(0, 0, 0, 0.2);

/* Deep overlay */
background: rgba(0, 0, 0, 0.3);
```

---

## Usage Guidelines

### Accent Color Rules

- Do not overuse the accent color
- Most of the UI should remain neutral
- Accent color should guide attention, not dominate
- Use for: primary buttons, active states, selected items, key highlights

### Text on Glass

- Primary text: white or near-white with opacity variation
- Secondary text: `rgba(255, 255, 255, 0.78)`
- Use shadows or subtle dark tinting for contrast when needed

### Interactive States

| State | Color Strategy |
|-------|---------------|
| Default | `--glass-bg` or `--glass-fill` |
| Hover | `--glass-bg-hover` or `--glass-fill-hover` |
| Active/Selected | `--glass-bg-active` or `--glass-fill-active` |
| Disabled | Reduced opacity (0.5) |

---

## Dark Mode Considerations

The Liquid Glass design works best with a light background. For dark mode:

- Invert glass backgrounds to dark tints
- Use `rgba(0, 0, 0, 0.4)` or similar for glass surface
- Maintain high contrast for text
- Reduce highlight intensity

---

## See Also

- [Glass Tokens](./glass.md) — Glass-specific effects and blur
- [Liquid Glass Guidelines](../guidelines/liquid-glass.md) — Full implementation guide
- [Quick Reference](../../references/quick-reference.md) — Condensed cheat sheet
