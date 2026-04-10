# Design Guidelines

## Philosophy
- User-friendliness is the highest priority
- Prioritize clarity and polish
- Keep everything simple, intuitive, and consistent
- Reduce cognitive load wherever possible

---

## Visual Design System: Apple Liquid Glass (iOS 26/macOS Tahoe)

### Overview
Apple Liquid Glass is the design language introduced at WWDC25. It features translucent, lensing UI elements that let content shine through while maintaining depth and hierarchy.

---

### Core Liquid Glass Principles

#### 1. Translucency is Key
- Content must shine through — users should feel they can see "into" the interface
- Use `rgba` backgrounds with low opacity (typically 0.08-0.12) for maximum transparency
- Avoid opaque surfaces that block the view

#### 2. Avoid Glass-on-Glass Stacking
- Never stack glass elements inside glass containers
- Glass should float as distinct layers with clear separation
- When nesting elements inside glass, use **fills** instead of additional glass layers

#### 3. Fills for Nested Elements
- Elements inside glass should use fill backgrounds, not glass:
  - Fill opacity: `rgba(255, 255, 255, 0.25)` for nested elements
  - Dark tint fills: `rgba(0, 0, 0, 0.015)` for contrast distinction
- This creates depth without layering translucency problems

#### 4. Lensing Effect via Backdrop Blur
- Apply `backdrop-filter: blur(48-56px)` to create the signature lensing effect
- Include `backdrop-filter: saturate(180%) brightness(1.1)` for Apple's optical feel
- Blur creates the "magnified through glass" appearance

#### 5. Rounded Floating Forms
- All glass elements should feel like floating, rounded forms
- Border radius: 20px for containers, 12px for smaller elements
- Margins: 12px between floating glass layers
- Subtle borders with low-opacity white to define edges

#### 6. Fluid Morphing Animations
- Use smooth cubic-bezier curves for transitions
- Spring-based timing: `cubic-bezier(0.25, 0.46, 0.45, 0.94)`
- Animations should feel organic, not mechanical

---

### CSS Token Values for Liquid Glass

```css
/* Glass Core */
--glass-bg: rgba(255, 255, 255, 0.08);
--glass-border: rgba(255, 255, 255, 0.18);
--glass-blur: 48px;
--glass-saturation: 180%;
--glass-brightness: 1.1;

/* Glass Shadows */
--glass-shadow: 
  0 8px 32px rgba(0, 0, 0, 0.08),
  0 4px 16px rgba(0, 0, 0, 0.04),
  inset 0 0.5px 0 rgba(255, 255, 255, 0.25);
--glass-shadow-float: 
  0 16px 48px rgba(0, 0, 0, 0.12),
  0 4px 12px rgba(0, 0, 0, 0.06);

/* Fills (for nested elements) */
--fill-white: rgba(255, 255, 255, 0.25);
--fill-dark: rgba(0, 0, 0, 0.015);

/* Transitions */
--transition-glass: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
```

---

### Typography for Liquid Glass UI

#### Font Stack (Apple-first with cross-platform fallbacks)
```css
font-family: 
  -apple-system, 
  BlinkMacSystemFont, 
  "SF Pro Display", 
  "SF Pro Text", 
  "Helvetica Neue", 
  Helvetica, 
  Arial, 
  sans-serif;
```

#### Font Weights
- Use regular (400) and medium (500) weights
- Avoid thin or heavy weights
- Letter spacing: slight positive tracking for headings

---

### Icon Style
- Use **stroke-based icons** with `stroke-width: 1.5` for SF Symbols aesthetic
- Icons should be clean, geometric, and consistent in weight
- Size: 20px for standard, 24px for larger

---

### Color Guidelines

#### Text on Glass
- Primary text: white or near-white with slight opacity variation
- Use shadows or subtle dark tinting for contrast when needed
- Modal content: 78% white (`rgba(255, 255, 255, 0.78)`) for readable contrast

#### Interactive Elements
- Send button: Black background (`#000000`) with white icon
- Active states: Subtle brightness increase
- Hover states: Slight opacity shifts

---

### Component-Specific Guidelines

#### Sidebar
- Floating glass with 12px margins, 20px border-radius
- Profile card: subtle dark tint for distinction
- Sign out button: centered, margin between profile card and footer

#### Chat Bubbles
- User messages: solid dark background (black), white text
- Agent messages: translucent glass bubbles with blur
- Differentiation through opacity, not layering

#### Modal/Overlay Background
- Semi-transparent dark overlay: `rgba(0, 0, 0, 0.4)`
- Modal background: NOT blurred (use solid fill for contrast)
- Modal content area: high contrast (78% white) for readability

#### Input Areas
- Glass styling with subtle border
- Focus states: slight glow or brightness shift
- Placeholder text: lower opacity white

---

### What NOT to Do in Liquid Glass
- ❌ Stack glass inside glass (use fills instead)
- ❌ Use heavy borders on glass elements
- ❌ Apply blur to modal backgrounds
- ❌ Use solid/opaque surfaces
- ❌ Sharp corners — everything should feel rounded
- ❌ Flat shadows — use layered, soft shadows

### Animation Timing Reference
- Quick interactions: 200ms
- Standard transitions: 400ms
- Page/modal transitions: 500-600ms
- Use `cubic-bezier(0.25, 0.46, 0.45, 0.94)` for organic feel

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
- **Primary accent:** Grass green
- Use it intentionally for:
- primary buttons
- active states
- selected items
- links or key highlights

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
