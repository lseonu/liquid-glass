# General Design Guidelines

Design guidelines for Santai — AI Creation Platform.

## Philosophy

- User-friendliness is the highest priority
- Prioritize clarity and polish
- Keep everything simple, intuitive, and consistent
- Reduce cognitive load wherever possible

---

## Core Principles

### 1. Simplicity First

- Avoid unnecessary UI elements
- Every component should have a clear purpose
- Prefer fewer options over overwhelming choices

### 2. Clarity

- The user should understand what to do immediately
- Navigation and actions should feel obvious
- Avoid clutter, visual noise, and over-explaining

### 3. Consistency

- Similar elements should always look and behave the same
- Reuse established patterns across the product
- Spacing, font sizes, border radii, and states should feel uniform

### 4. Friendliness

- The interface should feel approachable, not technical or harsh
- Use soft edges, balanced spacing, and readable typography
- Favor calm confidence over flashy design

---

## Visual Style

### General Feel

- Clean and minimal
- Spacious
- Modern but not trendy
- Premium without being decorative

### Accent Color

- **Primary accent:** Grass green (`#10B981`)
- Use it intentionally for:
  - Primary buttons
  - Active states
  - Selected items
  - Links or key highlights

### Color Rules

- Do not overuse the accent color
- Most of the UI should remain neutral
- Accent color should guide attention, not dominate the screen
- Maintain strong contrast and readability at all times

### Base Palette

- Backgrounds: white or soft neutral tones
- Text: dark gray or near-black
- Secondary text: muted gray
- Borders/dividers: subtle neutral tones

### Surfaces

- Use soft backgrounds and subtle separation between sections
- Avoid heavy borders
- Prefer light shadows, soft contrast, and rounded corners

### Rounded Edges

- Rounded corners should be standard across buttons, inputs, cards, modals, and containers
- Corners should feel soft and modern, not sharp or boxy

---

## Typography

### Font Direction

- Use a clean sans-serif font with subtle personality
- Fonts must be easy to read above all else
- Avoid fonts that are too decorative or stylized
- Keep fonts consistent

### Typography Rules

- Strong hierarchy between heading, subheading, body, and caption
- Use generous line height
- Avoid tiny text
- Prefer normal or medium weights over overly thin text
- Text should feel effortless to scan

### Tone of Typography

- Calm
- Crisp
- Unembellished
- Professional but human

---

## Layout & Spacing

### Spacing

- Use generous whitespace, letting elements breathe
- Avoid cramped layouts
- Group related items visually
- The UI should feel light, not packed
- Consistent spacing scale (e.g. 8px, 16px, 24px)

---

## Components

### Buttons

- Rounded
- Clear hierarchy between primary, secondary, and tertiary actions
- Primary buttons should feel prominent without being loud
- Avoid overly saturated or aggressive button styling

### Inputs

- Simple, clean borders
- Clearly indicate focus state
- Labels should always be visible (not just placeholders)

### Cards / Containers

- Rounded corners
- Subtle shadows (not heavy)
- Clear separation between sections

### Modals / Sheets

- Should feel focused and uncluttered
- One clear purpose per modal
- Easy to dismiss, easy to understand

---

## Interaction Design

### Feedback

- Every action should have visible feedback
  - Hover states
  - Click states
  - Loading indicators
- Feedback should reassure the user without distracting them

### Motion

- Motion should be minimal and smooth
- Avoid flashy animation
- Transitions should support clarity and polish

### Errors

- Clear, human-readable messages
- Never use vague system-like wording when a clearer message is possible (avoid "Something went wrong")

### States

- Design for:
  - Empty states
  - Loading states
  - Error states

---

## Accessibility

- Prioritize readability and contrast
- Avoid relying only on color to convey meaning
- Ensure UI is usable for a broad range of users
- Keep interactive elements comfortably sized
- Support keyboard navigation where possible

---

## Tone & Feel

- Calm, clean, and subtle
- Feels fast and responsive
- Friendly

### UI Writing Style Rules

- Prefer plain language
- Avoid jargon when possible
- Buttons and labels should say exactly what they do

---

## What to Optimize For

- Speed of understanding
- Ease of use for non-technical users
- Minimal friction in workflows

---

## Things to Prioritize in Every Design Decision

- Is it easy to understand?
- Is it easy to read?
- Does it feel calm and uncluttered?
- Does it help the user move forward quickly?
- Does it feel polished without drawing attention to itself?

---

## Things to Avoid

- Clutter
- Tiny text
- Harsh contrast combinations
- Too many colors
- Too many competing call-to-actions
- Heavy borders
- Sharp corners
- Overly playful or gimmicky UI
- Complex layouts when a simpler one works

---

## Rule of Thumb

If the interface feels busier than necessary, simplify it.
If it looks clever but not obvious, simplify it.
If it would confuse a first-time user, simplify it.

---

## See Also

- [Liquid Glass Design System](liquid-glass-design-system.md) ([[liquid-glass-design-system]]) — Full Liquid Glass implementation guide
- [Quick Reference](quick-reference.md) ([[quick-reference]]) — Condensed cheat sheet for common patterns
- [Color Palette](color-palette.md) ([[color-palette]]) — Complete color system documentation
- [Spacing System](spacing-system.md) ([[spacing-system]]) — Spacing scale and layout conventions
- [Component Patterns](component-patterns.md) ([[component-patterns]]) — Ready-to-use code snippets
- [Mockup Codebase Reference](../codebases/mockup.md) ([[mockup]]) — Working implementation reference
