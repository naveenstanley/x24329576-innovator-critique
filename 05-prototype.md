# ZenFox — Prototype & Design Specifications

## Product Overview

The ZenFox mobile app is the digital companion to the in-person Field Sessions programme. It is the primary daily touchpoint for Irish farmers engaging with nature-based mindfulness practices.

---

## Design Philosophy

**"Earthy, honest, unhurried."**

ZenFox must feel like stepping outside — not like opening a wellness app. Every design decision prioritises:
- Warmth over clinical coldness
- Simplicity over feature overload
- Irish landscape over stock photography
- Trust over gamification pressure

---

## Brand Identity

### Colour Palette

| Name | Hex | Usage |
|------|-----|-------|
| **Moss** | `#2D5016` | Primary — headers, CTAs, navigation |
| **Bark** | `#3E2C1C` | Text — body copy, labels |
| **Meadow** | `#7BA05B` | Secondary — accents, active states |
| **Foxglove** | `#C4713B` | Highlight — notifications, badges, fox icon |
| **Limestone** | `#F4F1EA` | Background — primary surface |
| **Mist** | `#E8E4DB` | Background — cards, containers |
| **Cloud** | `#FFFFFF` | Background — modals, overlays |

### Typography

| Role | Font | Weight | Size |
|------|------|--------|------|
| Display / H1 | **DM Serif Display** | Regular | 32px |
| H2 | **DM Serif Display** | Regular | 24px |
| Body | **Source Sans 3** | Regular (400) | 16px |
| Caption / Label | **Source Sans 3** | SemiBold (600) | 13px |
| Button | **Source Sans 3** | SemiBold (600) | 15px |

### Logo

A minimalist fox silhouette mid-stride, tail curving upward into a gentle spiral (evokes both a fox's brush and a meditative spiral). Rendered in Foxglove (#C4713B) on Limestone (#F4F1EA), or reversed on Moss (#2D5016).

### Iconography

Line-drawn icons at 24px, 1.5px stroke, Bark (#3E2C1C). Nature-themed: leaf, mountain, sun, raindrop, feather, paw print. No clinical/medical iconography.

---

## Core Screens (MVP)

### 1. Home Screen — "Today"

**Layout:** Full-width hero image (seasonal Irish landscape, changes monthly) with overlaid greeting. Below: today's session card, mood check-in prompt, streak counter.

```
┌─────────────────────────────┐
│  [Seasonal landscape photo] │
│                             │
│  Good morning, Seán.        │
│  Day 12 of your trail.      │
│                             │
├─────────────────────────────┤
│  ┌───────────────────────┐  │
│  │ 🌿 Today's Session    │  │
│  │ "Listening to Rain"   │  │
│  │ 8 min · Field audio   │  │
│  │          [▶ Play]     │  │
│  └───────────────────────┘  │
│                             │
│  How are you today?         │
│  [😟] [😐] [🙂] [😊] [🌟] │
│                             │
│  ┌───────────────────────┐  │
│  │ 🦊 Fox Spotting       │  │
│  │ Log what you noticed  │  │
│  │ today in the fields   │  │
│  │         [+ Add Entry] │  │
│  └───────────────────────┘  │
│                             │
│  [Home] [Trails] [Journal] [More] │
└─────────────────────────────┘
```

### 2. Audio Player Screen

**Layout:** Full-screen landscape photo background (blurred). Centred: session title, narrator name, waveform visualiser (gentle, organic wave shape), play/pause, 15s skip, timer. No distracting UI.

```
┌─────────────────────────────┐
│  [Blurred landscape bg]     │
│                             │
│       Listening to Rain     │
│     Narrated by Máirín      │
│                             │
│    ~~~~ waveform ~~~~       │
│                             │
│     ◁15  [ ▶ ]  15▷        │
│       3:24 / 8:00           │
│                             │
│  [Timer: Stop after 1 loop] │
└─────────────────────────────┘
```

### 3. Resilience Trails Screen

**Layout:** Vertical scroll of trail cards (8-week programmes). Each card: landscape thumbnail, trail name, season tag, progress bar, "Continue" CTA.

```
┌─────────────────────────────┐
│  Your Trails                │
│                             │
│  ┌───────────────────────┐  │
│  │ [Woodland image]      │  │
│  │ Spring Awakening      │  │
│  │ Week 3 of 8           │  │
│  │ ████████░░░░ 37%      │  │
│  │          [Continue →] │  │
│  └───────────────────────┘  │
│                             │
│  ┌───────────────────────┐  │
│  │ [Harvest field image]  │  │
│  │ Harvest Focus          │  │
│  │ Starts June            │  │
│  │          [Preview →]  │  │
│  └───────────────────────┘  │
│                             │
│  ┌───────────────────────┐  │
│  │ [Frost morning image]  │  │
│  │ Winter Rest            │  │
│  │ Starts November        │  │
│  │          [Preview →]  │  │
│  └───────────────────────┘  │
└─────────────────────────────┘
```

### 4. Fox Spotting Journal

**Layout:** Reverse-chronological feed of nature observation entries. Each entry: date, location tag, short text, optional photo thumbnail, weather icon. FAB button to add new entry.

### 5. Mood Tracker (Hidden Analytics)

**Layout:** Simple weekly calendar grid showing mood colours. Monthly trend line (subtle, not clinical). If 3+ days at lowest mood, gentle prompt: "It looks like things have been tough. Would you like to talk to someone? [Call IFA Helpline] [Not now]"

---

## Technical Specifications

| Spec | Detail |
|------|--------|
| **Platform** | iOS 15+ and Android 12+ (React Native) |
| **Backend** | Node.js + PostgreSQL on AWS (eu-west-1, Dublin region) |
| **Audio** | Pre-recorded MP3, streamed via CloudFront CDN |
| **Auth** | Email/password + Apple/Google SSO |
| **Data** | GDPR-compliant; mood data encrypted at rest (AES-256); no data shared with third parties |
| **Offline** | Audio sessions downloadable for offline use (critical for rural dead zones) |
| **Accessibility** | WCAG 2.1 AA; VoiceOver/TalkBack support; minimum 16px body text; high contrast mode |
| **Language** | English (primary), Irish/Gaeilge (planned for V2) |
| **Analytics** | PostHog (self-hosted, GDPR-compliant); anonymised usage patterns only |

---

## Prototype Deliverable

The accompanying HTML prototype (`index.html`) demonstrates the landing page for ZenFox, showcasing the brand identity, visual language, and core value propositions as they would appear to prospective users, partners, and funders visiting the ZenFox website.
