---
name: locomotion-styles
description: Show Locomotion style variants. Use when the user says "loco styles", "show styles", or asks about design themes/variants.
---

# Locomotion Style Variants

Every template is available in 6 styles. Default is free; the rest require Pro.

## Default (Free)
Clean and minimal. System font, 12px border-radius, thin borders, no shadows.
- Font: system-ui, sans-serif
- Borders: 1px solid #e5e5e5
- Border radius: 12px
- Shadows: none

## Brutalist (Pro)
Hard edges, thick borders, monospace font, offset shadows. Uppercase headings.
- Font: ui-monospace, monospace
- Borders: 3px solid #000000
- Border radius: 0px
- Shadows: 4px 4px 0px #000
- Text: uppercase headings, weight 900

## Rounded (Pro)
Soft corners, friendly feel. Pill-shaped badges, gentle shadows.
- Font: system-ui, sans-serif
- Borders: 1px solid #e5e5e5
- Border radius: 24px
- Shadows: 0 8px 32px rgba(0,0,0,0.08)

## Minimal (Pro)
Ultra-clean, whisper-thin. Light weight, wide spacing.
- Font: system-ui, sans-serif
- Borders: 0.5px solid #f0f0f0
- Border radius: 4px
- Shadows: none
- Weight: 400, spacing: 0.02em

## Glass (Pro)
Frosted glass, translucent layers. Gradient backgrounds.
- Font: system-ui, sans-serif
- Borders: 1px solid rgba(255,255,255,0.3)
- Border radius: 16px
- Background: linear-gradient(135deg, rgba(255,255,255,0.9), rgba(255,255,255,0.6))

## Neo (Pro)
Colored offset shadows, playful and bold. Thick borders.
- Font: system-ui, sans-serif
- Borders: 2px solid #171717
- Border radius: 14px
- Shadows: 3px 3px 0px #a3a3a3
- Weight: 700

## Using Styles

Pass the `variant` prop to any template composition:

```tsx
<FadeSlideUp text="Hello" variant="brutalist" />
```

Or fetch styled preview videos:
```
/videos/fade-slide-up-brutalist.mp4
/videos/fade-slide-up-rounded.mp4
/videos/fade-slide-up-minimal.mp4
/videos/fade-slide-up-glass.mp4
/videos/fade-slide-up-neo.mp4
```

Browse styles at https://locomotion.pro — use the style pills at the top of the template grid.
