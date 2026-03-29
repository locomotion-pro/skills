---
name: locomotion-remotion
description: Build professional Remotion video animations using Locomotion's template library. Use when creating animated videos, product demos, explainers, or SaaS marketing content with Remotion.
---

# Locomotion — Remotion Animation Templates

You are an expert at building Remotion video compositions using the Locomotion template library. When a user asks you to create animated videos, product tours, explainers, or marketing content, use these templates and patterns.

## API Access

Locomotion provides a REST API to discover and retrieve templates:

```bash
# List all templates
curl https://www.locomotion.pro/api/templates

# Filter by category
curl "https://www.locomotion.pro/api/templates?category=SaaS"
curl "https://www.locomotion.pro/api/templates?category=E-commerce"

# Filter by duration
curl "https://www.locomotion.pro/api/templates?duration=3"

# Get a specific template with source code
curl https://www.locomotion.pro/api/templates/fade-slide-up

# List categories
curl https://www.locomotion.pro/api/categories

# List style variants
curl https://www.locomotion.pro/api/styles
```

## Available Categories

Text, SaaS, Explainer, Data, Social, Branding, Product, E-commerce, Education, Finance, Healthcare, Real Estate, Recruitment, Events, Gaming

## Available Style Variants

- **default** — Clean and minimal (free)
- **brutalist** — Monospace font, sharp edges, thick borders, offset shadows
- **rounded** — Soft 24px corners, pill shapes, friendly feel
- **minimal** — Ultra-thin borders, light weight, wide spacing
- **glass** — Frosted gradients, translucent layers
- **neo** — Colored offset shadows, thick borders, playful

## Core Animation Patterns

All Locomotion templates use Remotion's frame-driven animation system. Never use CSS transitions or Framer Motion inside Remotion compositions — they won't render correctly.

### Essential Imports

```tsx
import { AbsoluteFill, useCurrentFrame, interpolate, spring, useVideoConfig, Sequence } from 'remotion';
```

### Fade + Slide Up (Most Common Pattern)

```tsx
const frame = useCurrentFrame();
const opacity = interpolate(frame, [0, 20], [0, 1], { extrapolateRight: 'clamp' });
const translateY = interpolate(frame, [0, 20], [24, 0], { extrapolateRight: 'clamp' });

<h1 style={{ opacity, transform: `translateY(${translateY}px)` }}>Hello World</h1>
```

### Spring Physics (Bouncy Entrances)

```tsx
const { fps } = useVideoConfig();
const scale = spring({ frame, fps, config: { stiffness: 200, damping: 12 } });

<div style={{ transform: `scale(${scale})` }}>Content</div>
```

### Staggered Animation

```tsx
{items.map((item, i) => {
  const delay = i * 8; // 8 frames between each
  const progress = spring({ frame: frame - delay, fps, config: { stiffness: 200, damping: 15 } });
  return <div style={{ opacity: progress }}>{item}</div>;
})}
```

### Sequencing Multiple Scenes

```tsx
<AbsoluteFill>
  <Sequence from={0} durationInFrames={90}>
    <FadeSlideUp text="Welcome" />
  </Sequence>
  <Sequence from={90} durationInFrames={150}>
    <FeatureShowcase />
  </Sequence>
  <Sequence from={240} durationInFrames={90}>
    <PricingComparison />
  </Sequence>
</AbsoluteFill>
```

## Template IDs Reference

### Text Animations (1-3s clips)
- `fade-slide-up` — Classic fade + slide up text entrance
- `spring-scale-in` — Bouncy spring scale for headlines
- `typewriter-reveal` — Character-by-character with blinking cursor
- `staggered-words` — Words fade in one by one
- `bold-text-punch` — Impact text on dark background (social clips)

### SaaS Product (3-5s clips)
- `saas-hero` — Hero with animated stats counter + CTA
- `feature-showcase` — Three feature cards fly in
- `pricing-comparison` — Animated pricing table
- `modal-explainer` — "How it Works" modal with steps
- `onboarding-flow` — Checklist with progress bar
- `drag-drop-demo` — Page builder blocks slide into place

### Data & Charts (3s clips)
- `bar-chart-reveal` — Animated bar chart
- `stats-dashboard` — Four-card metrics grid with counters

### Explainer (3-4s clips)
- `step-explainer` — Numbered steps with animated underlines
- `concept-breakdown` — "What is X?" with bullet points

### Social (1-3s clips)
- `quote-card` — Testimonial with author
- `bold-text-punch` — Impact text for social

### Branding (2-3s clips)
- `logo-reveal` — Logo mark with expanding ring
- `intro-outro` — Cinematic intro/outro card

### Product (3-4s clips)
- `app-feature-callout` — App mockup with callout badge
- `ui-walkthrough` — Animated cursor through app steps

### E-commerce (3s clips)
- `product-reveal` — Product card with price
- `discount-countdown` — Countdown timer
- `cart-animation` — Shopping cart flow

### Education (3s clips)
- `lesson-intro` — Lesson number + title
- `flashcard-flip` — Question/answer flip
- `quiz-result` — Score circle animation

### Finance (3s clips)
- `stock-ticker` — Market watch with prices
- `portfolio-breakdown` — Donut chart
- `payment-flow` — Three-step payment process

### Healthcare (3s clips)
- `patient-journey` — Four-step patient flow
- `appointment-booking` — Booking card with time slots
- `wellness-stats` — Health metrics cards

### Real Estate (3-4s clips)
- `property-tour` — Property card with details
- `listing-card` — Three property listings
- `virtual-walkthrough` — Room-by-room pan

### Recruitment (3s clips)
- `job-posting` — Job card with tags
- `team-intro` — Team member grid
- `culture-reel` — Company values on dark background

### Events (3s clips)
- `countdown-timer` — Days/hours/minutes countdown
- `agenda-reveal` — Event schedule
- `speaker-card` — Speaker profile

### Gaming (3s clips)
- `achievement-unlock` — Trophy + XP bar
- `leaderboard` — Player rankings
- `level-up` — Level number with progress bar

## When to Use This Skill

- User asks to "create a video", "make an animation", "build a product demo"
- User mentions Remotion, video templates, or animated content
- User wants marketing videos, explainer content, or social clips
- User asks for a specific animation type (pricing table, onboarding flow, etc.)

## Workflow

1. Understand what kind of video the user needs
2. Fetch the relevant template from the API: `curl https://www.locomotion.pro/api/templates/{id}`
3. Use the returned source code as a starting point
4. Customize props (text, colors) to match the user's brand
5. Compose multiple templates using `<Sequence>` for longer videos
6. Add transitions between scenes for polish

## Rules

- ALWAYS use `useCurrentFrame()` for animations — never CSS transitions
- ALWAYS use `interpolate()` with `extrapolateRight: 'clamp'` to prevent overflow
- Use `spring()` for organic, bouncy motion
- Use `<Sequence>` to compose multiple scenes with proper timing
- Use `<AbsoluteFill>` as the root container for every composition
- All compositions must be registered with `<Composition>` in Root.tsx
- Test with `npx remotion studio` before rendering
- Render with `npx remotion render` for final output
