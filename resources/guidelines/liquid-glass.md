# Liquid Glass Guidelines

Full implementation guide for Apple Liquid Glass UI components.

## Source Reference

This documentation is derived from the `mockup/` codebase at `/home/ubuntu/mockup/`. See [Mockup Codebase Reference](../../codebases/mockup.md) ([[mockup]]).

## Overview

Apple Liquid Glass is the design language introduced at WWDC25. It features translucent, lensing UI elements that let content shine through while maintaining depth and hierarchy.

---

## Component Patterns

### Sidebar

- Floating glass with 12px margins, 20px border-radius
- Profile card: subtle dark tint for distinction
- Sign out button: centered, margin between profile card and footer

```css
.sidebar {
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

From `design/principles/index.md`:

- **User-friendliness** is the highest priority
- **Clarity and polish** over complexity
- Keep everything **simple, intuitive, and consistent**
- **Reduce cognitive load** wherever possible
- The interface should feel **approachable, not technical or harsh**
- Use soft edges, balanced spacing, and readable typography
- Favor **calm confidence** over flashy design

---

## See Also

- [Design Principles](../principles/) — Core design philosophy
- [Liquid Glass Principles](../principles/liquid-glass.md) — Liquid Glass-specific principles
- [Tokens](../tokens/) — All CSS tokens
- [Component Patterns](../patterns/) — Ready-to-use code snippets
- [Quick Reference](../../references/quick-reference.md) — Condensed cheat sheet
- [Mockup Codebase Reference](../../codebases/mockup.md) — Working implementation reference
