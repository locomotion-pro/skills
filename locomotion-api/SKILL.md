---
name: locomotion-api
description: Locomotion API reference. Use when the user says "loco api", "api docs", or asks about the Locomotion REST API.
---

# Locomotion API Reference

Base URL: `https://locomotion.pro/api`

## Authentication

Source code requires an API key. Get one at locomotion.pro/dashboard.

```
Authorization: Bearer loco_YOUR_API_KEY
```

## Endpoints

### GET /api/templates

List all templates. Source code is never included in list view.

**Query parameters:**
| Param | Type | Description |
|-------|------|-------------|
| `category` | string | Filter by category (e.g. `SaaS`, `Text`) |
| `duration` | number | Filter by duration in seconds (1, 3, 5) |
| `tag` | string | Filter by tag (e.g. `fade`, `spring`) |
| `limit` | number | Max results (default 20, max 100) |
| `offset` | number | Pagination offset |

**Example:**
```bash
curl "https://locomotion.pro/api/templates?category=SaaS&limit=5"
```

**Response:**
```json
{
  "templates": [
    {
      "id": "saas-hero",
      "name": "SaaS Hero",
      "description": "Hero section with animated stats and CTA.",
      "duration": 3,
      "category": "SaaS",
      "tags": ["hero", "stats", "cta"],
      "fps": 30,
      "durationInFrames": 90,
      "width": 1920,
      "height": 1080,
      "editableProps": [{"key": "title", "type": "string", "label": "Title", "defaultValue": "Ship faster with AI"}],
      "styles": ["default", "brutalist", "rounded", "minimal", "glass", "neo"]
    }
  ],
  "total": 6,
  "limit": 5,
  "offset": 0,
  "categories": ["Text", "SaaS", "Data", ...]
}
```

### GET /api/templates/:id

Get a single template by ID.

- **Without API key:** Returns metadata only (no source code)
- **With API key:** Returns full template including source code

**Example:**
```bash
# Metadata only
curl https://locomotion.pro/api/templates/fade-slide-up

# With source code
curl -H "Authorization: Bearer loco_xxx" \
  https://locomotion.pro/api/templates/fade-slide-up
```

### GET /api/categories

List all available categories.

```bash
curl https://locomotion.pro/api/categories
```

**Response:**
```json
{
  "categories": ["Text", "SaaS", "Explainer", "Data", "Social", "Branding", "Product", "E-commerce", "Education", "Finance", "Healthcare", "Real Estate", "Recruitment", "Events", "Gaming"]
}
```

### GET /api/styles

List all style variants.

```bash
curl https://locomotion.pro/api/styles
```

**Response:**
```json
{
  "styles": [
    {"id": "default", "name": "Default", "description": "Clean and minimal", "isFree": true},
    {"id": "brutalist", "name": "Brutalist", "description": "Hard edges, thick borders, monospace", "isFree": false},
    ...
  ]
}
```

## Rate Limits

No rate limits currently. Be reasonable.

## Errors

| Status | Meaning |
|--------|---------|
| 200 | Success |
| 400 | Bad request (missing params) |
| 404 | Template not found |
| 405 | Method not allowed |
