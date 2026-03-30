---
name: locomotion-help
description: Show Locomotion help guide. Use when the user says "loco help", "locomotion help", or asks how to use Locomotion templates.
---

# Locomotion Help

Locomotion is a library of production-ready Remotion animation templates for video creation.

## Quick Start

```bash
# Install the skills
npx skills add locomotion-pro/skills

# Browse templates via API
curl https://locomotion.pro/api/templates

# Get a specific template
curl https://locomotion.pro/api/templates/fade-slide-up

# Get source code (requires API key)
curl -H "Authorization: Bearer loco_YOUR_KEY" \
  https://locomotion.pro/api/templates/fade-slide-up
```

## Available Commands

Ask me any of these:
- **"loco templates"** — Browse all 44 templates by category
- **"loco styles"** — See the 6 style variants (Default, Brutalist, Rounded, Minimal, Glass, Neo)
- **"loco api"** — API reference and authentication guide
- **"loco help"** — This help guide

## Getting an API Key

1. Sign up at **locomotion.pro**
2. Go to **locomotion.pro/dashboard**
3. Click "Generate key" — you'll get a `loco_` key
4. Use it: `curl -H "Authorization: Bearer loco_xxx" https://locomotion.pro/api/templates/fade-slide-up`

## Using Templates

1. Browse templates at **locomotion.pro** or via the API
2. Pick a template (e.g. `fade-slide-up`)
3. Get the source code via API with your key
4. Paste into your Remotion project
5. Customize props (text, colors, duration)
6. Render with `npx remotion render`

## Studio

Visit **locomotion.pro/studio** to:
- Drag templates onto a timeline
- Compose multi-scene videos
- Edit text and transitions
- Export full Remotion code

## Links

- Website: https://locomotion.pro
- Studio: https://locomotion.pro/studio
- API: https://locomotion.pro/api/templates
- Dashboard: https://locomotion.pro/dashboard
