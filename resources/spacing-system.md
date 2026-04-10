# Spacing & Layout System

Spacing scale and layout conventions for Santai's Liquid Glass UI.

## Spacing Scale

4px base unit.

| Token | Value | Pixels | Common Usage |
|-------|-------|--------|--------------|
| `--space-1` | `4px` | 4px | Tight gaps, icon margins |
| `--space-2` | `8px` | 8px | Between related items |
| `--space-3` | `12px` | 12px | Component padding |
| `--space-4` | `16px` | 16px | Section padding |
| `--space-5` | `20px` | 20px | Large gaps |
| `--space-6` | `24px` | 24px | Section separation |
| `--space-8` | `32px` | 32px | Major sections |
| `--space-10` | `40px` | 40px | Page margins |
| `--space-12` | `48px` | 48px | Large whitespace |
| `--space-16` | `64px` | 64px | Hero sections |

## Border Radius Scale

| Token | Value | Usage |
|-------|-------|-------|
| `--radius-sm` | `6px` | Small buttons, badges |
| `--radius-md` | `10px` | Inputs, small cards |
| `--radius-lg` | `14px` | Cards, panels |
| `--radius-xl` | `20px` | Modals, large containers |
| Pill | `100px` | Buttons, chips |

## Layout Constants

### Sidebar

```css
--sidebar-width-expanded:  240px;
--sidebar-width-collapsed: 68px;
```

### Content Max Width

```css
max-width: 960px;  /* Standard page content */
max-width: 680px;  /* Form/input areas */
```

## Spacing Guidelines

### Generous Whitespace

- Use generous whitespace, letting elements breathe
- The UI should feel light, not packed
- Avoid cramped layouts
- Group related items visually

### Component Spacing

| Context | Spacing |
|---------|---------|
| Between form fields | `--space-4` |
| Inside cards | `--space-4` to `--space-5` |
| Section separation | `--space-6` to `--space-8` |
| Page margins | `--space-6` to `--space-8` |
| Floating glass margins | `12px` |

### Glass Layer Margins

Between floating glass layers: `12px`

```css
/* Example: floating cards */
.card {
  margin: 12px;
  border-radius: 20px;
}
```

## Common Patterns

### Card Padding

```css
.card {
  padding: var(--space-4);
}
```

### Section Spacing

```css
.section {
  padding: var(--space-6) 0;
}
```

### Button Padding

```css
.btn {
  padding: 10px var(--space-4);  /* Vertical, Horizontal */
}
```

### Input Padding

```css
.input {
  padding: var(--space-3) var(--space-4);
}
```

### Icon + Text Gap

```css
.icon-text-group {
  gap: var(--space-2);  /* 8px between icon and label */
}
```

## See Also

- [Liquid Glass Design System](liquid-glass-design-system.md) ([[liquid-glass-design-system]]) — Full implementation guide with all CSS tokens
- [General Design Guidelines](general-design-guidelines.md) ([[general-design-guidelines]]) — Core design principles
- [Quick Reference](quick-reference.md) ([[quick-reference]]) — Condensed cheat sheet
- [Color Palette](color-palette.md) ([[color-palette]]) — Complete color system
- [Component Patterns](component-patterns.md) ([[component-patterns]]) — Ready-to-use code snippets
