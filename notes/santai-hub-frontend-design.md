# Santai Hub Frontend - Liquid Glass Implementation

Source: `/home/ubuntu/santai-hub/apps/frontend/`

## Overview

The Santai Hub frontend (Next.js + Tailwind CSS) provides a concrete web implementation of Apple's Liquid Glass design language.

---

## Design System Architecture

### Color System (OKLCH)

The frontend uses the OKLCH color space for modern, perceptual color handling:

```css
:root {
  --primary: oklch(0.65 0.19 163);      /* Blue-ish primary */
  --primary-foreground: oklch(1 0 0);
  --background: oklch(0.99 0 0);
  --foreground: oklch(0.145 0 0);
  --card: oklch(1 0 0);
  --muted: oklch(0.965 0 0);
  --border: oklch(0.91 0 0);
}
```

**Dark mode:**

```css
.dark {
  --background: oklch(0.12 0 0);
  --foreground: oklch(0.985 0 0);
  --primary: oklch(0.72 0.19 163);
  --border: oklch(1 0 0 / 10%);
}
```

---

## Glass Implementation

### Primary Glass (`.glass`)

High translucency, maximum blur for strong lensing effect:

```css
.glass {
  background: rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(48px) saturate(180%) brightness(1.1);
  -webkit-backdrop-filter: blur(48px) saturate(180%) brightness(1.1);
  border: 1px solid rgba(255, 255, 255, 0.18);
  box-shadow:
    0 8px 32px rgba(0, 0, 0, 0.06),
    0 4px 16px rgba(0, 0, 0, 0.03),
    inset 0 0.5px 0 rgba(255, 255, 255, 0.25);
}
```

### Subtle Glass (`.glass-subtle`)

Lower blur for areas needing more content legibility:

```css
.glass-subtle {
  background: rgba(255, 255, 255, 0.55);
  backdrop-filter: blur(24px) saturate(150%);
  -webkit-backdrop-filter: blur(24px) saturate(150%);
  border: 1px solid rgba(0, 0, 0, 0.06);
  box-shadow:
    0 4px 24px rgba(0, 0, 0, 0.04),
    0 1px 8px rgba(0, 0, 0, 0.02);
}
```

---

## Shadow System

### Soft Shadows

```css
.shadow-soft {
  box-shadow:
    0 2px 12px rgba(0, 0, 0, 0.04),
    0 1px 4px rgba(0, 0, 0, 0.02);
}

.shadow-soft-lg {
  box-shadow:
    0 8px 32px rgba(0, 0, 0, 0.06),
    0 2px 8px rgba(0, 0, 0, 0.03);
}

.shadow-float {
  box-shadow:
    0 16px 48px rgba(0, 0, 0, 0.1),
    0 4px 12px rgba(0, 0, 0, 0.04);
}
```

---

## Animation System

### Keyframe Animations

```css
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(8px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes slideUp {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

.animate-fade-in {
  animation: fadeIn 500ms cubic-bezier(0.25, 0.46, 0.45, 0.94) forwards;
}

.animate-slide-up {
  animation: slideUp 600ms cubic-bezier(0.25, 0.46, 0.45, 0.94) forwards;
  opacity: 0;
}
```

### Animation Classes

- `.animate-fade-in` — Subtle fade with slight upward movement
- `.animate-slide-up` — More dramatic slide from below
- `.delay-1` through `.delay-4` — Stagger delays (80ms increments)

### Reduced Motion Support

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## Typography

### Font Stack

```css
font-family: "Google Sans", "Google Sans Text", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
```

### Heading Styles (from page.tsx)

- H1: 5xl to 7xl, font-semibold, tracking-[-0.035em], leading-[1.05]
- H2: 4xl to 5xl, font-semibold, tracking-[-0.03em]
- H3: text-xl, font-semibold, tracking-tight

---

## Component Patterns

### Navbar

- Fixed position with `.glass-subtle` background
- Border: `border-border/50`
- Height: 14 (3.5rem)
- Max width: 5xl with px-6 padding

```tsx
<header className="fixed top-0 left-0 right-0 z-50 border-b border-border/50 glass-subtle">
```

### Cards

- Border: `border-border/40`
- Background: gradient from `card` to `muted/20`
- Shadow: `shadow-soft-lg`
- Border radius: 2xl

### Buttons

- Primary: rounded-xl, h-12, gap-2.5
- Outline: with `.shadow-soft`

### Selection Color

```css
::selection {
  background: oklch(0.72 0.19 163 / 25%);
}
```

---

## Layout Conventions

- Container max-width: `max-w-5xl` or `max-w-3xl`
- Section padding: py-32, px-6
- Grid: `grid sm:grid-cols-2 lg:grid-cols-4` for features
- Gap: 5 for cards, 4-5 for buttons

---

## Responsive Behavior

- Mobile-first approach
- Hidden elements on small screens: `hidden sm:flex`
- Flex direction: `flex-col sm:flex-row` for stacked/row layouts

---

## File Structure

```
apps/frontend/src/
├── app/
│   ├── globals.css          /* CSS variables, glass utilities, animations */
│   ├── layout.tsx          /* Root layout with navbar, footer */
│   ├── page.tsx            /* Hero, features, timeline sections */
│   └── components/
│       └── Navbar.tsx      /* Fixed glass navbar */
├── components/ui/         /* shadcn/ui components */
│   ├── button.tsx
│   ├── card.tsx
│   ├── badge.tsx
│   └── ...
└── lib/utils.ts            /* cn() utility for className merging */
```

---

## Dependencies

- **Tailwind CSS** — v4 with `@theme inline` for custom properties
- **shadcn/ui** — Component library base
- **framer-motion** — Motion components (HeroFadeIn, StaggerContainer, etc.)
- **next/image** — Optimized images

---

## Alignment with Apple Liquid Glass

| Aspect | Santai Hub | Apple Spec |
|--------|-----------|------------|
| Blur intensity | 48px (glass), 24px (subtle) | 48-56px for lensing |
| Saturate | 180% | 180-200% |
| Brightness | 1.1 | 1.1 |
| Border opacity | 18% white | 15-20% white |
| Inner highlight | inset 0 0.5px 0 | Yes |
| Animation timing | cubic-bezier(0.25, 0.46, 0.45, 0.94) | Spring curves |
| Reduced motion | Supported | Recommended |

---

## See Also

- [Liquid Glass Design System](../resources/liquid-glass-design-system.md) ([[liquid-glass-design-system]]) — Primary CSS implementation reference
- [Component Patterns](../resources/component-patterns.md) ([[component-patterns]]) — Reusable code snippets
- [Apple Liquid Glass Adoption Guide](../notes/apple-liquid-glass-adoption-guide.md) ([[apple-liquid-glass-adoption-guide]]) — Native platform context