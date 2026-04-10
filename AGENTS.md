# Santai Project

This directory is managed by Santai.

## Directory Structure

- **resources/** - Reference materials including markdown files, PDFs, images, and other documents
- **codebases/** - Code repositories and references
- **history/** - Markdown documentation of major changes and decisions (supplements git history)
- **notes/** - General notes, scratch space, and quick thoughts

## Design System Documentation

The `resources/` directory contains design system documentation:

> **⚠️ Primary Source: [general-design-guidelines.md](resources/general-design-guidelines.md) ([[general-design-guidelines]]) is the most authoritative design reference. When making any design decision, consult this document first. If guidance conflicts between documents, `general-design-guidelines.md` takes precedence.**

| Document | Description |
|----------|-------------|
| **[general-design-guidelines.md](resources/general-design-guidelines.md) ([[general-design-guidelines]])** | **🔑 PRIMARY — Core design principles, philosophy, and visual system. This is the source of truth for all design decisions.** |
| [liquid-glass-design-system.md](resources/liquid-glass-design-system.md) ([[liquid-glass-design-system]]) | Apple Liquid Glass implementation guide with CSS tokens, component patterns, and accessibility guidelines |
| [quick-reference.md](resources/quick-reference.md) ([[quick-reference]]) | Condensed cheat sheet for common patterns and tokens |
| [color-palette.md](resources/color-palette.md) ([[color-palette]]) | Complete color system documentation |
| [spacing-system.md](resources/spacing-system.md) ([[spacing-system]]) | Spacing scale and layout conventions |
| [component-patterns.md](resources/component-patterns.md) ([[component-patterns]]) | Ready-to-use code snippets for components |

These documents serve as the authoritative reference for the Santai UI/UX design system. **Always start with `general-design-guidelines.md` — it defines the overarching principles that all other documents support and elaborate on.**

### Codebase References

The `codebases/` directory contains references to implementations:

- [mockup.md](codebases/mockup.md) ([[mockup]]) - Reference to `/home/ubuntu/mockup/` containing the working Liquid Glass implementation

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
