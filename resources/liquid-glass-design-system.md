# Apple Liquid Glass Design System

Design system documentation for Santai's implementation of Apple's Liquid Glass design language (iOS 26/macOS Tahoe).

## Source Reference

This documentation is derived from the `mockup/` codebase at `/home/ubuntu/mockup/`, which contains the working implementation. See [Mockup Codebase Reference](../codebases/mockup.md) ([[mockup]]).

## Overview

Apple Liquid Glass is the design language introduced at WWDC25. It features translucent, lensing UI elements that let content shine through while maintaining depth and hierarchy.

---

## Core Principles

### 1. Translucency is Key

Content must shine through — users should feel they can see "into" the interface.

- Use `rgba` backgrounds with low opacity (typically 0.08-0.12) for maximum transparency
- Avoid opaque surfaces that block the view

### 2. Avoid Glass-on-Glass Stacking

- Never stack glass elements inside glass containers
- Glass should float as distinct layers with clear separation
- When nesting elements inside glass, use **fills** instead of additional glass layers

### 3. Fills for Nested Elements

Elements inside glass should use fill backgrounds, not glass:

- Fill opacity: `rgba(255, 255, 255, 0.25)` for nested elements
- Dark tint fills: `rgba(0, 0, 0, 0.015)` for contrast distinction

### 4. Lensing Effect via Backdrop Blur

- Apply `backdrop-filter: blur(48-56px)` to create the signature lensing effect
- Include `backdrop-filter: saturate(180%) brightness(1.1)` for Apple's optical feel
- Blur creates the "magnified through glass" appearance

### 5. Rounded Floating Forms

- All glass elements should feel like floating, rounded forms
- Border radius: 20px for containers, 12px for smaller elements
- Margins: 12px between floating glass layers
- Subtle borders with low-opacity white to define edges

### 6. Fluid Morphing Animations

- Use smooth cubic-bezier curves for transitions
- Spring-based timing: `cubic-bezier(0.25, 0.46, 0.45, 0.94)`
- Animations should feel organic, not mechanical

---

## CSS Token Values

### Glass Core

```css
:root {
  /* Glass surface — very transparent like real glass */
  --glass-bg:              rgba(255, 255, 255, 0.08);
  --glass-bg-hover:        rgba(255, 255, 255, 0.12);
  --glass-bg-active:       rgba(255, 255, 255, 0.18);
  --glass-bg-pressed:      rgba(255, 255, 255, 0.05);
  
  /* Blur & vibrancy — strong blur creates lensing effect */
  --glass-blur:            56px;
  --glass-blur-intense:    72px;
  --glass-saturate:        200%;
  --glass-brightness:      1.1;
  
  /* Highlights — light reflections on glass edges */
  --glass-highlight:       rgba(255, 255, 255, 0.5);
  --glass-highlight-soft:  rgba(255, 255, 255, 0.25);
  
  /* Border — thin luminous edge */
  --glass-border:          rgba(255, 255, 255, 0.18);
  
  /* Shadows — provides separation, adapts to content */
  --glass-shadow:          0 4px 24px rgba(0, 0, 0, 0.06), 
                           0 1px 6px rgba(0, 0, 0, 0.04);
  --glass-shadow-elevated: 0 16px 56px rgba(0, 0, 0, 0.10), 
                           0 6px 20px rgba(0, 0, 0, 0.06);
  
  /* Inner highlight — top edge light reflection */
  --glass-inner-highlight: inset 0 0.5px 0 var(--glass-highlight);
  
  /* Fills for elements INSIDE glass (avoid glass on glass) */
  --glass-fill:            rgba(255, 255, 255, 0.12);
  --glass-fill-hover:      rgba(255, 255, 255, 0.20);
  --glass-fill-active:     rgba(255, 255, 255, 0.28);
}
```

### Transitions (Apple Spring Curves)

```css
:root {
  --transition-fast:   150ms cubic-bezier(0.23, 1, 0.32, 1);
  --transition-base:   250ms cubic-bezier(0.23, 1, 0.32, 1);
  --transition-slow:   400ms cubic-bezier(0.23, 1, 0.32, 1);
  --transition-spring: 500ms cubic-bezier(0.175, 0.885, 0.32, 1.1);
}
```

---

## Typography

### Font Stack

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

### Font Sizes

```css
--font-size-xs:      0.75rem;   /* 12px */
--font-size-sm:      0.8125rem; /* 13px */
--font-size-base:    0.875rem;  /* 14px */
--font-size-md:      1rem;      /* 16px */
--font-size-lg:      1.25rem;   /* 20px */
--font-size-xl:      1.5rem;    /* 24px */
--font-size-2xl:     2rem;      /* 32px */
```

### Font Weights

- Use regular (400) and medium (500) weights
- Avoid thin or heavy weights
- Letter spacing: slight positive tracking for headings

### Icon Style

- Use **stroke-based icons** with `stroke-width: 1.5` for SF Symbols aesthetic
- Icons should be clean, geometric, and consistent in weight
- Size: 20px for standard, 24px for larger

---

## Color Guidelines

### Accent Color

- **Primary accent:** Grass green (`#10B981`)
- Use it intentionally for primary buttons, active states, selected items, and key highlights

### Text on Glass

- Primary text: white or near-white with slight opacity variation
- Use shadows or subtle dark tinting for contrast when needed
- Modal content: 78% white (`rgba(255, 255, 255, 0.78)`) for readable contrast

### Interactive Elements

- Send button: Black background (`#000000`) with white icon
- Active states: Subtle brightness increase
- Hover states: Slight opacity shifts

---

## Component Patterns

### Sidebar

- Floating glass with 12px margins, 20px border-radius
- Profile card: subtle dark tint for distinction
- Sign out button: centered, margin between profile card and footer

```css
.sidebar {
  /* Liquid Glass — highly translucent */
  background: var(--glass-bg);
  backdrop-filter: 
    blur(var(--glass-blur)) 
    saturate(var(--glass-saturate)) 
    brightness(var(--glass-brightness));
  
  border-radius: 20px;
  border: 0.5px solid var(--glass-border);
  box-shadow: var(--glass-shadow), var(--glass-inner-highlight);
}
```

### Chat Bubbles

- User messages: solid dark background (black), white text
- Agent messages: translucent glass bubbles with blur
- Differentiation through opacity, not layering

```css
.creation-chat__bubble--user {
  background: var(--color-text-primary);
  color: #fff;
  border-bottom-right-radius: 4px;
}

.creation-chat__bubble--agent {
  background: rgba(255, 255, 255, 0.12);
  backdrop-filter: blur(48px) saturate(180%);
  border: 1px solid rgba(255, 255, 255, 0.15);
  border-radius: 16px;
  box-shadow: 0 4px 24px rgba(0, 0, 0, 0.06), inset 0 0.5px 0 rgba(255, 255, 255, 0.4);
}
```

### Input Areas

- Glass styling with subtle border
- Focus states: slight glow or brightness shift
- Placeholder text: lower opacity white

```css
.creation-chat-sidebar__input-wrapper {
  background: rgba(255, 255, 255, 0.12);
  backdrop-filter: blur(48px) saturate(180%);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 20px;
}

.creation-chat-sidebar__input-wrapper:focus-within {
  background: rgba(255, 255, 255, 0.2);
  border-color: rgba(255, 255, 255, 0.3);
  box-shadow: 0 4px 32px rgba(0, 0, 0, 0.08), inset 0 0.5px 0 rgba(255, 255, 255, 0.5);
}
```

### Form Cards

```css
.creation-form-card {
  background: rgba(255, 255, 255, 0.12);
  backdrop-filter: blur(48px) saturate(180%);
  border: 1px solid rgba(255, 255, 255, 0.15);
  border-radius: 16px;
  box-shadow: 0 4px 24px rgba(0, 0, 0, 0.06), inset 0 0.5px 0 rgba(255, 255, 255, 0.4);
}
```

### Modals

- Semi-transparent dark overlay: `rgba(0, 0, 0, 0.2-0.3)`
- Modal background: NOT blurred (use solid fill for contrast) or intense blur
- Modal content area: high contrast for readability

```css
.login-modal-overlay {
  background: rgba(0, 0, 0, 0.2);
  backdrop-filter: blur(8px) saturate(180%);
}

.login-modal {
  background: rgba(255, 255, 255, 0.85);
  backdrop-filter: blur(56px) saturate(200%) brightness(1.1);
  border-radius: 20px;
  border: 0.5px solid rgba(255, 255, 255, 0.5);
  box-shadow: 0 24px 64px rgba(0, 0, 0, 0.12), inset 0 0.5px 0 rgba(255, 255, 255, 0.8);
}
```

### Glass Checkbox

```css
.creation-glass-checkbox__box {
  background: rgba(255, 255, 255, 0.4);
  backdrop-filter: blur(12px) saturate(180%);
  border: 1px solid rgba(255, 255, 255, 0.3);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.04), inset 0 1px 0 rgba(255, 255, 255, 0.4);
}

.creation-glass-checkbox__input:checked ~ .creation-glass-checkbox__box {
  background: var(--color-accent);
  border-color: transparent;
  box-shadow: 0 4px 12px rgba(16, 185, 129, 0.2), inset 0 1px 0 rgba(255, 255, 255, 0.3);
}
```

---

## Animation Timing Reference

| Type | Duration | Easing |
|------|----------|--------|
| Quick interactions | 150ms | `cubic-bezier(0.23, 1, 0.32, 1)` |
| Standard transitions | 200-250ms | `cubic-bezier(0.4, 0, 0.2, 1)` |
| Page/modal transitions | 300-400ms | `cubic-bezier(0.4, 0, 0.2, 1)` |
| Spring animations | 500ms | `cubic-bezier(0.175, 0.885, 0.32, 1.1)` |

---

## What NOT to Do in Liquid Glass

- ❌ Stack glass inside glass (use fills instead)
- ❌ Use heavy borders on glass elements
- ❌ Apply blur to modal backgrounds (use solid fill or intense blur for legibility)
- ❌ Use solid/opaque surfaces
- ❌ Sharp corners — everything should feel rounded
- ❌ Flat shadows — use layered, soft shadows

---

## Accessibility

- Prioritize readability and contrast
- Avoid relying only on color to convey meaning
- Ensure UI is usable for a broad range of users
- Keep interactive elements comfortably sized
- Support keyboard navigation
- Support `prefers-reduced-motion`

```css
@media (prefers-reduced-motion: reduce) {
  * {
    transition: none;
    animation: none;
  }
}
```

---

## Scrollbar Styling

Apple-style minimal scrollbar:

```css
::-webkit-scrollbar {
  width: 6px;
  height: 6px;
}

::-webkit-scrollbar-track {
  background: transparent;
}

::-webkit-scrollbar-thumb {
  background: rgba(0, 0, 0, 0.12);
  border-radius: 3px;
}

::-webkit-scrollbar-thumb:hover {
  background: rgba(0, 0, 0, 0.20);
}
```

---

## Implementation Files

Key implementation files in `mockup/src/`:

- `index.css` - Global design tokens and reset
- `components/layout/Sidebar.css` - Sidebar with Liquid Glass styling
- `components/layout/Layout.css` - Layout wrapper styles
- `pages/Creation/Creation.css` - Chat interface, modals, form cards
- `components/create/PromptBox.css` - Input box with glass effect
- `components/auth/LoginModal.css` - Authentication modal

---

## Design Philosophy

From `DESIGN_GUIDELINES.md`:

- **User-friendliness** is the highest priority
- **Clarity and polish** over complexity
- Keep everything **simple, intuitive, and consistent**
- **Reduce cognitive load** wherever possible
- The interface should feel **approachable, not technical or harsh**
- Use soft edges, balanced spacing, and readable typography
- Favor **calm confidence** over flashy design

---

## See Also

- [General Design Guidelines](general-design-guidelines.md) ([[general-design-guidelines]]) — Core design principles and philosophy
- [Quick Reference](quick-reference.md) ([[quick-reference]]) — Condensed cheat sheet for common patterns
- [Color Palette](color-palette.md) ([[color-palette]]) — Complete color system documentation
- [Spacing System](spacing-system.md) ([[spacing-system]]) — Spacing scale and layout conventions
- [Component Patterns](component-patterns.md) ([[component-patterns]]) — Ready-to-use code snippets
- [Mockup Codebase Reference](../codebases/mockup.md) ([[mockup]]) — Working implementation reference
- [Apple Liquid Glass Adoption Guide](../notes/apple-liquid-glass-adoption-guide.md) ([[apple-liquid-glass-adoption-guide]]) — Native platform adoption notes
- [Design System Migration](../history/2026-04-09-design-system-migration.md) ([[2026-04-09-design-system-migration]]) — Migration history
