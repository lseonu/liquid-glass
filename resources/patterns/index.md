# Component Patterns

Ready-to-use code snippets for common Liquid Glass components.

## Glass Card

```css
.glass-card {
  background: rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(56px) saturate(200%) brightness(1.1);
  -webkit-backdrop-filter: blur(56px) saturate(200%) brightness(1.1);
  border: 0.5px solid rgba(255, 255, 255, 0.18);
  border-radius: 20px;
  box-shadow: 
    0 4px 24px rgba(0, 0, 0, 0.06),
    0 1px 6px rgba(0, 0, 0, 0.04),
    inset 0 0.5px 0 rgba(255, 255, 255, 0.5);
  padding: var(--space-4);
}
```

## Glass Card with Hover

```css
.glass-card {
  transition: 
    background 250ms cubic-bezier(0.4, 0, 0.2, 1),
    box-shadow 250ms cubic-bezier(0.4, 0, 0.2, 1);
}

.glass-card:hover {
  background: rgba(255, 255, 255, 0.12);
  box-shadow: 
    0 8px 32px rgba(0, 0, 0, 0.08),
    0 2px 8px rgba(0, 0, 0, 0.06),
    inset 0 0.5px 0 rgba(255, 255, 255, 0.6);
}
```

## Glass Button (Ghost)

```css
.glass-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: var(--space-2);
  padding: 10px var(--space-4);
  border-radius: 100px;
  background: rgba(255, 255, 255, 0.12);
  backdrop-filter: blur(24px) saturate(180%);
  -webkit-backdrop-filter: blur(24px) saturate(180%);
  border: 1px solid rgba(255, 255, 255, 0.2);
  color: var(--color-text-primary);
  font-size: var(--font-size-sm);
  font-weight: var(--font-weight-medium);
  cursor: pointer;
  transition: all 200ms cubic-bezier(0.4, 0, 0.2, 1);
}

.glass-btn:hover {
  background: rgba(255, 255, 255, 0.2);
  border-color: rgba(255, 255, 255, 0.3);
}

.glass-btn:active {
  transform: scale(0.97);
}
```

## Primary Button (Solid)

```css
.primary-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: var(--space-2);
  padding: 10px var(--space-4);
  border-radius: 100px;
  background: var(--color-accent);
  color: white;
  font-size: var(--font-size-sm);
  font-weight: var(--font-weight-medium);
  border: none;
  cursor: pointer;
  transition: all 200ms cubic-bezier(0.4, 0, 0.2, 1);
}

.primary-btn:hover {
  background: var(--color-accent-hover);
}

.primary-btn:active {
  transform: scale(0.97);
}
```

## Glass Input

```css
.glass-input-wrapper {
  display: flex;
  align-items: center;
  gap: var(--space-2);
  background: rgba(255, 255, 255, 0.12);
  backdrop-filter: blur(48px) saturate(180%);
  -webkit-backdrop-filter: blur(48px) saturate(180%);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 20px;
  padding: var(--space-2) var(--space-3);
  transition: all 250ms cubic-bezier(0.4, 0, 0.2, 1);
}

.glass-input-wrapper:focus-within {
  background: rgba(255, 255, 255, 0.2);
  border-color: rgba(255, 255, 255, 0.3);
  box-shadow: 
    0 4px 32px rgba(0, 0, 0, 0.08),
    inset 0 0.5px 0 rgba(255, 255, 255, 0.5);
}

.glass-input {
  flex: 1;
  border: none;
  outline: none;
  background: transparent;
  font-family: inherit;
  font-size: var(--font-size-base);
  color: var(--color-text-primary);
}

.glass-input::placeholder {
  color: var(--color-text-tertiary);
}
```

## Glass Textarea

```css
.glass-textarea {
  padding: 12px var(--space-4);
  border-radius: 14px;
  font-size: var(--font-size-sm);
  font-family: inherit;
  background: rgba(255, 255, 255, 0.5);
  backdrop-filter: blur(24px) saturate(180%);
  -webkit-backdrop-filter: blur(24px) saturate(180%);
  border: 1px solid rgba(255, 255, 255, 0.35);
  color: var(--color-text-primary);
  outline: none;
  resize: none;
  line-height: 1.5;
  transition: all 200ms cubic-bezier(0.4, 0, 0.2, 1);
  box-shadow: inset 0 0.5px 0 rgba(255, 255, 255, 0.5);
}

.glass-textarea:focus {
  background: rgba(255, 255, 255, 0.6);
  border-color: rgba(255, 255, 255, 0.45);
}

.glass-textarea::placeholder {
  color: var(--color-text-tertiary);
}
```

## Glass Modal

```css
.modal-overlay {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.2);
  backdrop-filter: blur(8px) saturate(180%);
  -webkit-backdrop-filter: blur(8px) saturate(180%);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.modal {
  width: 100%;
  max-width: 480px;
  background: rgba(255, 255, 255, 0.85);
  backdrop-filter: blur(56px) saturate(200%) brightness(1.1);
  -webkit-backdrop-filter: blur(56px) saturate(200%) brightness(1.1);
  border-radius: 20px;
  border: 0.5px solid rgba(255, 255, 255, 0.5);
  box-shadow: 
    0 24px 64px rgba(0, 0, 0, 0.12),
    0 8px 24px rgba(0, 0, 0, 0.08),
    inset 0 0.5px 0 rgba(255, 255, 255, 0.8);
}
```

## Glass Checkbox

```css
.glass-checkbox {
  display: flex;
  align-items: center;
  gap: 8px;
  cursor: pointer;
}

.glass-checkbox__input {
  position: absolute;
  opacity: 0;
  pointer-events: none;
}

.glass-checkbox__box {
  width: 20px;
  height: 20px;
  border-radius: 6px;
  background: rgba(255, 255, 255, 0.4);
  backdrop-filter: blur(12px) saturate(180%);
  -webkit-backdrop-filter: blur(12px) saturate(180%);
  border: 1px solid rgba(255, 255, 255, 0.3);
  box-shadow: 
    0 2px 4px rgba(0, 0, 0, 0.04),
    inset 0 1px 0 rgba(255, 255, 255, 0.4);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 200ms cubic-bezier(0.4, 0, 0.2, 1);
}

.glass-checkbox__input:checked ~ .glass-checkbox__box {
  background: var(--color-accent);
  border-color: transparent;
  box-shadow: 
    0 4px 12px rgba(16, 185, 129, 0.2),
    inset 0 1px 0 rgba(255, 255, 255, 0.3);
}

.glass-checkbox__icon {
  color: white;
  opacity: 0;
  transform: scale(0.5);
  transition: all 200ms cubic-bezier(0.4, 0, 0.2, 1);
}

.glass-checkbox__input:checked ~ .glass-checkbox__box .glass-checkbox__icon {
  opacity: 1;
  transform: scale(1);
}
```

## Icon Button (Circle)

```css
.icon-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 38px;
  height: 38px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.2);
  color: var(--color-text-secondary);
  border: none;
  cursor: pointer;
  transition: all 200ms cubic-bezier(0.4, 0, 0.2, 1);
}

.icon-btn:hover {
  background: rgba(255, 255, 255, 0.35);
  color: var(--color-text-primary);
}

.icon-btn:active {
  transform: scale(0.95);
}

/* Active variant */
.icon-btn--active {
  background: var(--color-text-primary);
  color: white;
}
```

## Avatar

```css
.avatar {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: var(--font-size-sm);
  font-weight: var(--font-weight-semibold);
  border: 2px solid rgba(255, 255, 255, 0.8);
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
}
```

## Chat Bubble (User)

```css
.chat-bubble--user {
  background: var(--color-text-primary);
  color: white;
  border-radius: 16px 16px 4px 16px;
  padding: var(--space-3) var(--space-4);
  max-width: 80%;
}
```

## Chat Bubble (Agent)

```css
.chat-bubble--agent {
  background: rgba(255, 255, 255, 0.12);
  backdrop-filter: blur(48px) saturate(180%);
  -webkit-backdrop-filter: blur(48px) saturate(180%);
  border: 1px solid rgba(255, 255, 255, 0.15);
  border-radius: 16px;
  box-shadow: 
    0 4px 24px rgba(0, 0, 0, 0.06),
    inset 0 0.5px 0 rgba(255, 255, 255, 0.4);
  padding: var(--space-3) var(--space-4);
  max-width: 80%;
}
```

## Loading Spinner

```css
.spinner {
  width: 14px;
  height: 14px;
  border: 2px solid rgba(255, 255, 255, 0.2);
  border-top-color: var(--color-accent);
  border-radius: 50%;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}
```

## Typing Indicator

```css
.typing-indicator {
  display: flex;
  gap: 4px;
  padding: 12px 16px;
  background: rgba(255, 255, 255, 0.12);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 16px;
}

.typing-indicator span {
  width: 6px;
  height: 6px;
  background: var(--color-text-tertiary);
  border-radius: 50%;
  animation: typingBounce 1.2s infinite ease-in-out;
}

.typing-indicator span:nth-child(2) { animation-delay: 0.15s; }
.typing-indicator span:nth-child(3) { animation-delay: 0.3s; }

@keyframes typingBounce {
  0%, 60%, 100% { transform: translateY(0); opacity: 0.4; }
  30% { transform: translateY(-4px); opacity: 1; }
}
```

---

## See Also

- [Liquid Glass Guidelines](../guidelines/liquid-glass.md) — Full implementation guide
- [Design Principles](../principles/) — Core design philosophy
- [Tokens](../tokens/) — All CSS tokens
