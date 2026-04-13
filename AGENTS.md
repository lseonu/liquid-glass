# Santai Project

This directory is managed by Santai. It contains the Liquid Glass design system knowledge base.

## Directory Structure

```
liquid-glass/
├── design/                    # Design system documentation
│   ├── principles/            # Core design philosophy
│   │   ├── index.md          # General design principles
│   │   └── liquid-glass.md   # Liquid Glass specific principles
│   ├── tokens/               # CSS tokens and variables
│   │   ├── colors.md        # Color system
│   │   ├── glass.md         # Glass-specific tokens (blur, shadows)
│   │   ├── spacing.md        # Spacing scale
│   │   └── typography.md     # Typography system
│   ├── patterns/            # Ready-to-use component patterns
│   │   └── index.md         # Component code snippets
│   └── guidelines/          # Implementation guidelines
│       └── liquid-glass.md # Full Liquid Glass implementation
├── references/               # Quick reference materials
│   └── quick-reference.md   # Condensed cheat sheet
├── codebases/                 # Implementation codebases
│   └── mockup.md            # Reference to /home/ubuntu/mockup/
├── history/                   # Change documentation
└── notes/                     # Scratch space
```

---

## Design System (Primary Source)

> **⚠️ Primary Source: `design/principles/index.md` is the most authoritative design reference. When making any design decision, consult this document first.**

### Quick Navigation

| Category | File | Purpose |
|----------|------|---------|
| **Philosophy** | `design/principles/index.md` | Core principles (simplicity, clarity, consistency) |
| **Liquid Glass** | `design/principles/liquid-glass.md` | The 6 Liquid Glass rules |
| **Implementation** | `design/guidelines/liquid-glass.md` | Full component implementation |
| **Tokens** | `design/tokens/` | All CSS tokens (colors, spacing, typography, glass) |
| **Patterns** | `design/patterns/index.md` | Ready-to-use code snippets |
| **Cheat Sheet** | `references/quick-reference.md` | Quick lookup for common patterns |

---

## AI Agent Vibe Coding Instructions

When building UI with this design system, AI agents should:

### 1. Read Before Coding

Start by reading these files:
- `design/principles/index.md` — Core design philosophy
- `design/principles/liquid-glass.md` — The 6 Liquid Glass principles
- `references/quick-reference.md` — Keep this open for quick lookups

### 2. Use Tokens, Don't Hardcode

Always use CSS tokens:
```css
/* Good */
background: var(--glass-bg);
border-radius: var(--radius-xl);

/* Bad */
background: rgba(255, 255, 255, 0.08);
border-radius: 20px;
```

### 3. Golden Rules for Liquid Glass

**DO:**
- ✅ Use `rgba(255, 255, 255, 0.08)` for glass backgrounds
- ✅ Apply `backdrop-filter: blur(56px) saturate(200%) brightness(1.1)`
- ✅ Use `border-radius: 20px` for containers
- ✅ Add inner highlights: `inset 0 0.5px 0 rgba(255, 255, 255, 0.5)`
- ✅ Use fills (`rgba(255, 255, 255, 0.12)`) inside glass

**DON'T:**
- ❌ Stack glass inside glass (use fills instead)
- ❌ Use heavy borders
- ❌ Apply blur to modal backgrounds
- ❌ Use opaque surfaces
- ❌ Sharp corners

### 4. Common Pattern

```css
.glass-card {
  background: var(--glass-bg);
  backdrop-filter: blur(56px) saturate(200%) brightness(1.1);
  -webkit-backdrop-filter: blur(56px) saturate(200%) brightness(1.1);
  border: 0.5px solid var(--glass-border);
  border-radius: 20px;
  box-shadow: 0 4px 24px rgba(0, 0, 0, 0.06), inset 0 0.5px 0 rgba(255, 255, 255, 0.5);
  padding: 16px;
}
```

### 5. Accessibility

- Support `prefers-reduced-motion`
- Ensure sufficient contrast
- Support keyboard navigation

### Full Instructions

See `references/vibe-coding.md` for complete vibe coding workflow.

---

## Pre-commit Hooks

This project uses [prek](https://prek.j178.dev/) to run [rumdl](https://github.com/rvben/rumdl) for markdown linting.

## History Convention

The `history/` directory contains markdown files documenting significant changes:

- Use filenames in format: `YYYY-MM-DD-brief-description.md`
- Document the what, why, and any alternatives considered
- Git tracks the granular changes; history/ captures the narrative

## Notes Convention

The `notes/` directory is for general notes and scratch space:

- Use `.md` or `.txt` files
- Name files descriptively (e.g., `meeting-notes.md`, `ideas.txt`)
- Notes are displayed with previews in the dashboard

---

## Codebase References

The `codebases/` directory contains references to implementations:

- [mockup.md](codebases/mockup.md) ([[mockup]]) - Reference to `/home/ubuntu/mockup/` containing the working Liquid Glass implementation
