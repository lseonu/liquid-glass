# Design System Migration

## Date

2026-04-09

## Summary

Migrated comprehensive design system documentation from `mockup/` to `liquid-glass/` repository.

## What Was Migrated

### From `mockup/DESIGN_GUIDELINES.md`

- Complete Apple Liquid Glass design system documentation
- Core design principles and philosophy
- CSS token values for glass effects
- Typography guidelines
- Color system with accent color
- Component-specific guidelines
- Animation timing references
- Accessibility considerations

### From `mockup/src/index.css`

- Complete CSS custom properties (design tokens)
- Glass effect variable definitions
- Color palette
- Typography scale
- Spacing system
- Border radii
- Shadow definitions
- Transition timings
- Scrollbar styling

### From `mockup/src/**/*.css`

Component-level implementation patterns including:

- Sidebar (`Sidebar.css`) - Full Liquid Glass implementation
- Layout (`Layout.css`) - Layout wrapper styles
- Creation workspace (`Creation.css`) - Chat interface, modals, form cards
- PromptBox (`PromptBox.css`) - Glass input container
- LoginModal (`LoginModal.css`) - Glass modal patterns

### From `mockup/README.md`

- Tech stack documentation
- Project structure
- Design tokens reference
- Development guidelines

## Destination Files

Created in `liquid-glass/resources/`:

1. [liquid-glass-design-system.md](../resources/liquid-glass-design-system.md) ([[liquid-glass-design-system]]) - Comprehensive Liquid Glass implementation guide
2. [general-design-guidelines.md](../resources/general-design-guidelines.md) ([[general-design-guidelines]]) - Core design principles and philosophy

## Why This Migration

The `liquid-glass/` repository serves as the central knowledge base for the Liquid Glass design language. Moving design documentation here ensures:

1. **Single source of truth** - Design decisions are documented in the repo that bears the design's name
2. **Long-term maintainability** - As the mockup evolves, this repo retains the core design principles
3. **Accessibility** - Design documentation is available to all team members working on any codebase
4. **Separation of concerns** - Design knowledge is decoupled from implementation details

## Relation to Codebase

The `mockup/` directory at `/home/ubuntu/mockup/` contains the working implementation that these documents reference. Key implementation files include:

- `src/index.css` - Design tokens and reset
- `src/components/layout/Sidebar.css` - Liquid Glass sidebar
- `src/pages/Creation/Creation.css` - Chat UI with glass effects
- `src/components/create/PromptBox.css` - Glass input component
- `src/components/auth/LoginModal.css` - Glass modal

## Alternatives Considered

1. **Keep documentation only in mockup**: Rejected because the mockup is primarily an implementation reference, not a design knowledge base.

2. **Create separate design repo**: Rejected to avoid fragmentation. The `liquid-glass/` repo already exists for this purpose.

3. **Update existing AGENTS.md**: The existing AGENTS.md focuses on project structure conventions. The new design docs complement but don't replace it.

## Notes

The implementation in `mockup/` serves as the canonical reference for how these design patterns should be implemented. The documentation in `liquid-glass/resources/` captures the "why" and "what" while the code captures the "how".

## See Also

- [Mockup Codebase Reference](../codebases/mockup.md) ([[mockup]]) — Working implementation reference
- [Quick Reference](../resources/quick-reference.md) ([[quick-reference]]) — Common patterns cheat sheet
- [Color Palette](../resources/color-palette.md) ([[color-palette]]) — Color system
- [Spacing System](../resources/spacing-system.md) ([[spacing-system]]) — Spacing scale and layout
- [Component Patterns](../resources/component-patterns.md) ([[component-patterns]]) — Ready-to-use code snippets
