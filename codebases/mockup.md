# Mockup Codebase Reference

Reference for the mockup implementation of the Liquid Glass design system.

## Location

`/home/ubuntu/mockup/`

## Description

A desktop-first React web application serving as the primary implementation reference for Santai's Liquid Glass design system. Contains working examples of all major UI patterns.

## Tech Stack

| Layer | Tool |
|-------|------|
| Build | Vite |
| Framework | React 19 |
| Routing | React Router v7 |
| Styling | Vanilla CSS + design tokens |
| Typography | Inter (Google Fonts) |

## Key Implementation Files

### Design Tokens

- `src/index.css` - Complete CSS custom properties including glass variables, colors, typography, spacing, and transitions

### Components

- `src/components/layout/Sidebar.css` - Liquid Glass sidebar implementation
- `src/components/layout/Layout.css` - Layout wrapper styles
- `src/components/auth/LoginModal.css` - Glass authentication modal
- `src/components/create/PromptBox.css` - Glass input container
- `src/components/create/SuggestionCard.css` - Card component styles

### Pages

- `src/pages/Creation/Creation.css` - Chat workspace with glass effects (1748 lines of patterns)
- `src/pages/Home/Home.css` - Home page styles
- `src/pages/Explore/Explore.css` - Explore page styles
- `src/pages/Create/Create.css` - Create page styles
- `src/pages/Login/Login.css` - Login page styles

### Assets

- `public/` - Images and icons used throughout the UI

## Component Patterns Available

The mockup contains working implementations of:

- Floating glass containers with backdrop blur
- Glass sidebar (expandable/collapsible)
- Glass input fields and textareas
- Glass buttons (ghost, primary, icon)
- Glass modals and overlays
- Chat bubbles (user/agent variants)
- Glass checkboxes and form controls
- Typing indicators
- Build progress steps
- Profile cards with avatar
- Form cards with option selection

## Usage

This codebase serves as the **implementation reference** for the Liquid Glass design system. Use it to:

1. See working examples of design patterns
2. Copy CSS properties and values
3. Understand component composition
4. Verify implementation details

The design documentation in `liquid-glass/resources/` captures the principles and patterns; this mockup shows them in action.

## Status

Active development - design system is being refined through implementation.
