---
name: locomotion-templates
description: List and browse Locomotion Remotion templates. Use when the user says "loco templates", "show templates", "list templates", or asks what templates are available.
---

# Locomotion Templates

44 base templates across 15 categories. Each available in 6 style variants = 264+ variations.

## Text Animations
| ID | Name | Duration | Editable |
|----|------|----------|----------|
| `fade-slide-up` | Fade Slide Up | 1s | text |
| `spring-scale-in` | Spring Scale In | 1s | text |
| `typewriter-reveal` | Typewriter Reveal | 3s | text |
| `staggered-words` | Staggered Words | 3s | text |
| `bold-text-punch` | Bold Text Punch | 1s | text |

## SaaS
| ID | Name | Duration | Editable |
|----|------|----------|----------|
| `saas-hero` | SaaS Hero | 3s | title |
| `feature-showcase` | Feature Showcase | 5s | — |
| `pricing-comparison` | Pricing Comparison | 3s | — |
| `modal-explainer` | Modal Explainer | 5s | — |
| `onboarding-flow` | Onboarding Flow | 5s | — |
| `drag-drop-demo` | Drag & Drop Demo | 5s | — |

## Data & Charts
| ID | Name | Duration |
|----|------|----------|
| `bar-chart-reveal` | Bar Chart Reveal | 3s |
| `stats-dashboard` | Stats Dashboard | 3s |

## Explainer
| ID | Name | Duration | Editable |
|----|------|----------|----------|
| `step-explainer` | Step Explainer | 3s | title |
| `concept-breakdown` | Concept Breakdown | 4s | title |

## Social
| ID | Name | Duration | Editable |
|----|------|----------|----------|
| `bold-text-punch` | Bold Text Punch | 1s | text |
| `quote-card` | Quote Card | 3s | text |

## Branding
| ID | Name | Duration | Editable |
|----|------|----------|----------|
| `logo-reveal` | Logo Reveal | 2s | text |
| `intro-outro` | Intro / Outro | 3s | text |

## Product
| ID | Name | Duration | Editable |
|----|------|----------|----------|
| `app-feature-callout` | App Feature Callout | 3s | text |
| `ui-walkthrough` | UI Walkthrough | 4s | — |

## E-commerce
| ID | Name | Duration | Editable |
|----|------|----------|----------|
| `product-reveal` | Product Reveal | 3s | text |
| `discount-countdown` | Discount Countdown | 3s | text |
| `cart-animation` | Cart Animation | 3s | — |

## Education
| ID | Name | Duration | Editable |
|----|------|----------|----------|
| `lesson-intro` | Lesson Intro | 3s | text |
| `flashcard-flip` | Flashcard Flip | 3s | text |
| `quiz-result` | Quiz Result | 3s | — |

## Finance
| ID | Name | Duration |
|----|------|----------|
| `stock-ticker` | Stock Ticker | 3s |
| `portfolio-breakdown` | Portfolio Breakdown | 3s |
| `payment-flow` | Payment Flow | 3s |

## Healthcare
| ID | Name | Duration |
|----|------|----------|
| `patient-journey` | Patient Journey | 3s |
| `appointment-booking` | Appointment Booking | 3s |
| `wellness-stats` | Wellness Stats | 3s |

## Real Estate
| ID | Name | Duration | Editable |
|----|------|----------|----------|
| `property-tour` | Property Tour | 3s | text |
| `listing-card` | Listing Card | 3s | — |
| `virtual-walkthrough` | Virtual Walkthrough | 4s | — |

## Recruitment
| ID | Name | Duration | Editable |
|----|------|----------|----------|
| `job-posting` | Job Posting | 3s | text |
| `team-intro` | Team Intro | 3s | — |
| `culture-reel` | Culture Reel | 3s | text |

## Events
| ID | Name | Duration | Editable |
|----|------|----------|----------|
| `countdown-timer` | Countdown Timer | 3s | text |
| `agenda-reveal` | Agenda Reveal | 3s | text |
| `speaker-card` | Speaker Card | 3s | text |

## Gaming
| ID | Name | Duration | Editable |
|----|------|----------|----------|
| `achievement-unlock` | Achievement Unlock | 3s | text |
| `leaderboard` | Leaderboard | 3s | — |
| `level-up` | Level Up | 3s | — |

## Usage

To use any template, fetch it from the API:

```bash
curl -H "Authorization: Bearer loco_YOUR_KEY" \
  https://locomotion.pro/api/templates/TEMPLATE_ID
```

Or browse interactively at https://locomotion.pro
