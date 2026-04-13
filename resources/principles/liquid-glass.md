# Liquid Glass Principles

Apple Liquid Glass is the design language introduced at WWDC25. It features translucent, lensing UI elements that let content shine through while maintaining depth and hierarchy.

---

## Core Principles

### 1. Translucency is Key

- Content must shine through — users should feel they can see "into" the interface
- Use `rgba` backgrounds with low opacity (typically 0.08-0.12) for maximum transparency
- Avoid opaque surfaces that block the view

### 2. Avoid Glass-on-Glass Stacking

- Never stack glass elements inside glass containers
- Glass should float as distinct layers with clear separation
- When nesting elements inside glass, use **fills** instead of additional glass layers

### 3. Fills for Nested Elements

- Elements inside glass should use fill backgrounds, not glass:
  - Fill opacity: `rgba(255, 255, 255, 0.25)` for nested elements
  - Dark tint fills: `rgba(0, 0, 0, 0.015)` for contrast distinction
- This creates depth without layering translucency problems

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

## See Also

- [Design Principles](./index.md) — Core design philosophy
- [Glass Tokens](../tokens/glass.md) — Glass-specific CSS tokens
- [Liquid Glass Guidelines](../guidelines/liquid-glass.md) — Full implementation guide
- [Component Patterns](../patterns/) — Ready-to-use code snippets
