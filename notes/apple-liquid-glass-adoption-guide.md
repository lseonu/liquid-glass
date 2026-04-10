# Apple Liquid Glass Adoption Guide Notes

Source: https://developer.apple.com/documentation/TechnologyOverviews/adopting-liquid-glass

## Overview

Adopting Liquid Glass doesn't require reinventing your app. Start by building in the latest Xcode to see automatic changes.

## Visual Refresh

- **Liquid Glass**: New dynamic material combining optical properties of glass with fluidity
- Forms a distinct functional layer for controls and navigation elements
- Adapts in response to overlap, focus state, and other factors

### Automatic Adoption via System Frameworks

Standard components automatically adopt Liquid Glass:
- Bars, sheets, popovers, controls

**SwiftUI:**
- `NavigationStack`
- `NavigationSplitView`
- `View.toolbar(content:)`

**UIKit:**
- `UINavigationBar`
- `UISplitViewController`

**AppKit:**
- Native components auto-adopt

### Custom Views

Apply Liquid Glass manually to custom views:

**SwiftUI:**
```swift
View.glassEffect(_:in:)
```

**UIKit:**
- `UIGlassEffect`

**AppKit:**
- `NSGlassEffectView`

## App Icons

- Dynamic, expressive design with layered appearance
- Respond dynamically to lighting and system effects
- **Variants**: light, dark, clear, tinted (iOS, iPadOS, macOS)
- Use **Icon Composer** (Xcode) or Apple Design Resources

## Controls

Refreshed look across platforms, animated on interaction.

**SwiftUI:**
```swift
PrimitiveButtonStyle.glass
```

**UIKit:**
```swift
UIButton.Configuration.glass()
```

**AppKit:**
```swift
NSButton.BezelStyle.glass
```

## Navigation

- Tab bars and sidebars float in Liquid Glass layer
- Focus stays on underlying content
- Establish clear navigation hierarchy

**SwiftUI:**
- `TabViewStyle.sidebarAdaptable`

## Search

- Global search experience across platforms
- `Tab(role: .search)` in SwiftUI
- `UISearchTab` in UIKit

## Key WWDC 2025 Videos

- Session 219: Meet Liquid Glass
- Session 356, 323, 284, 310: Various Liquid Glass topics

## Reference

- SwiftUI docs: `Applying Liquid Glass to custom views`
- HIG: Human Interface Guidelines for Liquid Glass
- Landmarks sample app: Demonstrates Liquid Glass implementation

## See Also

- [Liquid Glass Design System](../resources/liquid-glass-design-system.md) ([[liquid-glass-design-system]]) — Santai's CSS implementation of Liquid Glass
- [General Design Guidelines](../resources/general-design-guidelines.md) ([[general-design-guidelines]]) — Core design principles
- [Quick Reference](../resources/quick-reference.md) ([[quick-reference]]) — Common patterns cheat sheet
- [Component Patterns](../resources/component-patterns.md) ([[component-patterns]]) — Ready-to-use CSS code snippets
- [Mockup Codebase Reference](../codebases/mockup.md) ([[mockup]]) — Working implementation reference
