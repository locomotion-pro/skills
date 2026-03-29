---
name: locomotion-remotion
description: Build professional Remotion video animations using Locomotion's template library. Use when creating animated videos, product demos, explainers, or SaaS marketing content with Remotion.
---

# Locomotion — Remotion Animation Templates

You are an expert at building Remotion video compositions using the Locomotion template library. When a user asks you to create animated videos, product tours, explainers, or marketing content, use these templates and patterns.

## API Access

Locomotion provides a REST API to discover and retrieve templates.

**Public (no auth):** Browse templates, get metadata, filter by category.
**Authenticated:** Get full source code. Requires API key from locomotion.pro/dashboard.

```bash
# List all templates (public)
curl https://www.locomotion.pro/api/templates

# Filter by category (public)
curl "https://www.locomotion.pro/api/templates?category=SaaS"

# Get template metadata (public)
curl https://www.locomotion.pro/api/templates/fade-slide-up

# Get template with source code (requires API key)
curl -H "Authorization: Bearer loco_YOUR_KEY" https://www.locomotion.pro/api/templates/fade-slide-up

# List categories (public)
curl https://www.locomotion.pro/api/categories

# List style variants (public)
curl https://www.locomotion.pro/api/styles
```

## Getting an API Key

1. Sign up at locomotion.pro
2. Go to locomotion.pro/dashboard
3. Generate an API key (starts with `loco_`)
4. Pass it as `Authorization: Bearer loco_xxx` header

## Available Categories

Text, SaaS, Explainer, Data, Social, Branding, Product, E-commerce, Education, Finance, Healthcare, Real Estate, Recruitment, Events, Gaming

## Core Remotion Patterns

All Locomotion templates use Remotion's frame-driven animation system. Never use CSS transitions or Framer Motion inside Remotion compositions.

### Essential Imports

```tsx
import { AbsoluteFill, useCurrentFrame, interpolate, spring, useVideoConfig, Sequence } from 'remotion';
```

### Fade + Slide Up

```tsx
const frame = useCurrentFrame();
const opacity = interpolate(frame, [0, 20], [0, 1], { extrapolateRight: 'clamp' });
const translateY = interpolate(frame, [0, 20], [24, 0], { extrapolateRight: 'clamp' });
```

### Spring Physics

```tsx
const { fps } = useVideoConfig();
const scale = spring({ frame, fps, config: { stiffness: 200, damping: 12 } });
```

### Staggered Animation

```tsx
items.map((item, i) => {
  const delay = i * 8;
  const progress = spring({ frame: frame - delay, fps, config: { stiffness: 200, damping: 15 } });
  return <div style={{ opacity: progress }}>{item}</div>;
})
```

### Sequencing Scenes

```tsx
<AbsoluteFill>
  <Sequence from={0} durationInFrames={90}>
    <SceneOne />
  </Sequence>
  <Sequence from={90} durationInFrames={150}>
    <SceneTwo />
  </Sequence>
</AbsoluteFill>
```

## Workflow

1. Understand what kind of video the user needs
2. Browse templates: `curl https://www.locomotion.pro/api/templates?category=SaaS`
3. Get the template source: `curl -H "Authorization: Bearer loco_xxx" https://www.locomotion.pro/api/templates/{id}`
4. Customize props (text, colors) to match the user's brand
5. Compose multiple templates using `<Sequence>` for longer videos
6. Register with `<Composition>` in Root.tsx
7. Preview with `npx remotion studio`, render with `npx remotion render`

## When to Use

- User asks to create a video, animation, or product demo
- User mentions Remotion or animated content
- User wants marketing videos, explainers, or social clips
- User needs a specific animation (pricing table, onboarding flow, etc.)

## Rules

- ALWAYS use `useCurrentFrame()` — never CSS transitions inside Remotion
- ALWAYS use `interpolate()` with `extrapolateRight: 'clamp'`
- Use `spring()` for bouncy, organic motion
- Use `<Sequence>` for multi-scene compositions
- Use `<AbsoluteFill>` as root container
- Fetch source code from the API — don't hardcode templates
