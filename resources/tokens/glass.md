# Glass Tokens

CSS tokens specifically for Liquid Glass effects.

## Glass Core

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
  --glass-brightness:       1.1;
  
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

## Transitions (Apple Spring Curves)

```css
:root {
  --transition-fast:   150ms cubic-bezier(0.23, 1, 0.32, 1);
  --transition-base:   250ms cubic-bezier(0.23, 1, 0.32, 1);
  --transition-slow:   400ms cubic-bezier(0.23, 1, 0.32, 1);
  --transition-spring: 500ms cubic-bezier(0.175, 0.885, 0.32, 1.1);
}
```

## Shadows

```css
--shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.04);
--shadow-md: 0 2px 8px rgba(0, 0, 0, 0.06);
--shadow-lg: 0 4px 16px rgba(0, 0, 0, 0.08);

/* Glass-specific shadows */
--glass-shadow: 
  0 8px 32px rgba(0, 0, 0, 0.08),
  0 4px 16px rgba(0, 0, 0, 0.04),
  inset 0 0.5px 0 rgba(255, 255, 255, 0.25);
--glass-shadow-float: 
  0 16px 48px rgba(0, 0, 0, 0.12),
  0 4px 12px rgba(0, 0, 0, 0.06);
```

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

## Accessibility

Support `prefers-reduced-motion`:

```css
@media (prefers-reduced-motion: reduce) {
  * {
    transition: none;
    animation: none;
  }
}
```

---

## See Also

- [Liquid Glass Principles](../principles/liquid-glass.md) — Core Liquid Glass principles
- [Color Tokens](./colors.md) — Glass color system
- [Liquid Glass Guidelines](../guidelines/liquid-glass.md) — Full implementation guide
