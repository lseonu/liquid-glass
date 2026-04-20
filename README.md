# liquid-glass

Santai design system project implementing Apple Liquid Glass UI/UX patterns.

## Quick Start

- **Design System**: See `design/` folder for complete documentation
- **Working Demo**: Open `/home/ubuntu/mockup/` — see [Mockup Reference](codebases/mockup.md)
- **Cheat Sheet**: See `references/quick-reference.md`

## Project Structure

```
liquid-glass/
├── design/                    # Design system documentation
│   ├── principles/            # Core design philosophy
│   │   ├── index.md          # General design principles
│   │   └── liquid-glass.md   # Liquid Glass specific principles
│   ├── tokens/               # CSS tokens and variables
│   │   ├── colors.md        # Color system
│   │   ├── glass.md         # Glass-specific tokens
│   │   ├── spacing.md        # Spacing scale 
│   │   └── typography.md     # Typography system
│   ├── patterns/            # Ready-to-use component patterns
│   │   └── index.md         # Component code snippets
│   └── guidelines/          # Implementation guidelines
│       └── liquid-glass.md # Full Liquid Glass implementation
├── references/               # Quick reference materials
│   └── quick-reference.md   # Condensed cheat sheet
├── codebases/                 # References to implementation codebases
│   └── mockup.md            # Mockup reference
├── history/                   # Change documentation
└── notes/                     # Scratch space
```

## Key Files

| Category | File | Purpose |
|----------|------|---------|
| Philosophy | `design/principles/index.md` | Core design principles |
| Liquid Glass | `design/principles/liquid-glass.md` | The 6 Liquid Glass rules |
| Implementation | `design/guidelines/liquid-glass.md` | Full component guide |
| Tokens | `design/tokens/` | All CSS tokens |
| Patterns | `design/patterns/index.md` | Ready-to-use snippets |
| Cheat Sheet | `references/quick-reference.md` | Quick lookup |

## AI Agents

See [AGENTS.md](AGENTS.md) for vibe coding instructions.

## Commands

- Markdown linting runs automatically on commit (via prek + rumdl)
