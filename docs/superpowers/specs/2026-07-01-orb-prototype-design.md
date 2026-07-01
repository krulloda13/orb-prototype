# Orb — Fitness Bracelet App Prototype

## Overview

Orb is a jewelry fitness bracelet companion app. The prototype is a web app (HTML/CSS/JS) with mobile-responsive layout, using hardcoded mock data. No backend or API integration.

**Target customer:** Fashion-forward individuals (gender-neutral) who care about health stats but don't want to wear something that looks like tech.

**Price positioning:** Accessible luxury ($150–$250), competing with Oura/Whoop.

**Brand direction:** Obsidian — dark mode, matte gold accents, architectural precision, luxury watch energy.

## Brand System

### Colors

| Token | Value | Usage |
|-------|-------|-------|
| `--bg-primary` | `#0A0A0C` | Page background |
| `--bg-card` | `rgba(255,255,255,0.04)` | Card surfaces |
| `--border-card` | `rgba(255,255,255,0.06)` | Card borders |
| `--bg-elevated` | `#111113` | Elevated surfaces, nav bar |
| `--accent` | `#C9A96E` | Matte gold — rings, active states, key data |
| `--accent-dim` | `rgba(201,169,110,0.35)` | Secondary rings, subtle gold |
| `--text-primary` | `#FFFFFF` | Headings, stat values |
| `--text-secondary` | `rgba(255,255,255,0.4)` | Labels, subtitles, units |
| `--text-tertiary` | `rgba(255,255,255,0.2)` | Inactive nav, dividers |

### Typography

- **Font:** DM Sans (Google Fonts)
- **Wordmark:** lowercase "orb", font-weight 300, font-size 20px
- **Stat values:** weight 300, large size, letter-spacing -0.5px
- **Labels:** weight 500, 10-11px, uppercase, opacity 0.4
- **Headings:** weight 300, 26px, letter-spacing -0.5px
- **Body:** weight 400, 14px

### Radii & Spacing

- Cards: 16px border-radius
- Buttons/pills: 12px
- Phone-width layout: max-width 390px, centered
- Card padding: 16px
- Section gap: 16px
- Screen padding: 20px horizontal

## Navigation

Bottom tab bar, fixed, 5 tabs:

1. **Home** (house icon) — default active
2. **Sleep** (moon icon)
3. **Activity** (flame icon)
4. **Heart** (heart icon)
5. **Profile** (person icon)

Active tab: gold icon + label. Inactive: `--text-tertiary`.

Tab bar background: `--bg-elevated` with top border `--border-card`.

## Screens

### 1. Home

- **Greeting:** "Good morning, Kris" (weight 300, 26px) with date below
- **Readiness ring:** Large centered SVG (160px), dual ring (outer = readiness, inner = recovery), gold stroke, score number centered inside (weight 300, 48px), "readiness" label below
- **Stat cards:** 2x2 grid
  - Sleep: "7h 24m" with moon icon
  - Heart Rate: "62 bpm" with heart icon
  - Steps: "8,240" with shoe icon
  - Calories: "420 kcal" with flame icon
- Cards are tappable — navigate to corresponding tab

### 2. Sleep

- **Sleep score ring:** Centered, similar to readiness ring but labeled "sleep score", value "85"
- **Sleep stages bar:** Horizontal stacked bar showing:
  - Awake (white/light): 23m
  - REM (gold): 1h 48m
  - Light (dim gold): 3h 42m
  - Deep (bright gold): 1h 31m
- **Stats row:** Time in bed (7h 52m) | Time asleep (7h 24m) | Efficiency (94%)
- **Nightly HR chart:** Simple line chart, x-axis = 10pm–6am, y-axis = bpm, showing dip during deep sleep. Gold line with subtle gradient fill below.

### 3. Activity

- **Move goal ring:** Large centered ring showing progress toward daily goal (e.g., 420/500 cal), gold stroke
- **Stat cards:** 3-column row
  - Steps: 8,240
  - Calories: 420 kcal
  - Active: 42 min
- **Hourly activity chart:** 24 vertical bars (one per hour), gold fill for active hours, dim for inactive. X-axis labels at 6am, 12pm, 6pm, 12am.

### 4. Heart Rate

- **Current BPM:** Large display "62 bpm" with a subtle pulse animation on the number
- **Resting HR badge:** Small pill showing "Resting: 58 bpm"
- **24-hour chart:** Line chart, x-axis = 12am–now, y-axis = bpm range. Gold line with gradient fill. Show current time marker.
- **Daily stats row:** Min (52) | Avg (68) | Max (124)

### 5. Profile

- **Device card:** "Orb Bracelet" with connection status (green dot = connected), battery level (82%), last synced time
- **User info card:** Name, age, weight, height — display only
- **Goals card:** Step goal (10,000), sleep goal (8h), calorie goal (500 kcal) — displayed as editable-looking fields but non-functional in prototype

## Data

All mock data, hardcoded. Representative realistic values for a healthy adult.

### Mock Data Values

| Metric | Value |
|--------|-------|
| Readiness score | 82 |
| Sleep score | 85 |
| Total sleep | 7h 24m |
| Time in bed | 7h 52m |
| Sleep efficiency | 94% |
| REM | 1h 48m |
| Light sleep | 3h 42m |
| Deep sleep | 1h 31m |
| Awake | 23m |
| Resting HR | 58 bpm |
| Current HR | 62 bpm |
| HR min | 52 |
| HR avg | 68 |
| HR max | 124 |
| Steps | 8,240 |
| Calories | 420 kcal |
| Active minutes | 42 min |
| Step goal | 10,000 |
| Sleep goal | 8h |
| Calorie goal | 500 kcal |
| Battery | 82% |

## Interactions

- Tab switching with active state
- Card taps navigate to detail tabs
- Smooth fade/slide transitions between screens
- Pulse animation on current heart rate
- Floating orb animation on readiness ring hover

## Tech Stack

- Single `index.html` file with embedded CSS and JS
- No frameworks, no build step
- DM Sans via Google Fonts CDN
- SVG for rings and charts
- Canvas or SVG for line/bar charts
- CSS transitions for screen switching

## Out of Scope

- Backend / API integration
- Real Apple Health or Google Fit data
- Push notifications
- Onboarding flow
- Authentication
- App store deployment
