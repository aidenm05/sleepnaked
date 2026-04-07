# Wireframes – Sleep Naked

This document describes the wireframe layouts for the core screens of the Sleep Naked application. Detailed visual assets will be maintained in `design/assets/`.

---

## Screen Inventory

| ID | Screen Name | Platform |
|----|-------------|----------|
| W-01 | Splash Screen | Mobile & Web |
| W-02 | Welcome / Onboarding | Mobile & Web |
| W-03 | Sign Up | Mobile & Web |
| W-04 | Log In | Mobile & Web |
| W-05 | Home Dashboard | Mobile & Web |
| W-06 | Log Sleep | Mobile |
| W-07 | Sleep Score Result | Mobile & Web |
| W-08 | Trends | Mobile & Web |
| W-09 | Recommendations | Mobile & Web |
| W-10 | Settings | Mobile & Web |

---

## W-01 – Splash Screen

```
┌──────────────────────────┐
│                          │
│                          │
│       [App Logo]         │
│      Sleep Naked         │
│                          │
│     ████████████         │
│     (loading bar)        │
│                          │
└──────────────────────────┘
```

---

## W-02 – Welcome / Onboarding

```
┌──────────────────────────┐
│   [Illustration]         │
│                          │
│  Better sleep starts     │
│      tonight.            │
│                          │
│  ┌──────────────────┐    │
│  │   Get Started    │    │
│  └──────────────────┘    │
│                          │
│  Already have an         │
│  account? [Log In]       │
└──────────────────────────┘
```

---

## W-03 – Sign Up

```
┌──────────────────────────┐
│  ←   Create Account      │
│                          │
│  Name                    │
│  ┌──────────────────┐    │
│  │                  │    │
│  └──────────────────┘    │
│                          │
│  Email                   │
│  ┌──────────────────┐    │
│  │                  │    │
│  └──────────────────┘    │
│                          │
│  Password                │
│  ┌──────────────────┐    │
│  │                  │    │
│  └──────────────────┘    │
│                          │
│  ┌──────────────────┐    │
│  │    Sign Up       │    │
│  └──────────────────┘    │
└──────────────────────────┘
```

---

## W-05 – Home Dashboard

```
┌──────────────────────────┐
│  Good evening, Alex  [👤]│
│                          │
│  ┌────────────────────┐  │
│  │  Last Night        │  │
│  │  Sleep Score: 78   │  │
│  │  ████████░░  7h 2m │  │
│  └────────────────────┘  │
│                          │
│  ┌────────────────────┐  │
│  │  Tonight's Tip     │  │
│  │  Avoid screens 1hr │  │
│  │  before bed. [→]   │  │
│  └────────────────────┘  │
│                          │
│  ┌──────────────────┐    │
│  │   + Log Sleep    │    │
│  └──────────────────┘    │
│                          │
│  [Home] [Trends] [Tips] [⚙]│
└──────────────────────────┘
```

---

## W-06 – Log Sleep

```
┌──────────────────────────┐
│  ←   Log Sleep           │
│                          │
│  Bedtime                 │
│  ┌──────────────────┐    │
│  │     11:00 PM     │    │
│  └──────────────────┘    │
│                          │
│  Wake Time               │
│  ┌──────────────────┐    │
│  │      7:00 AM     │    │
│  └──────────────────┘    │
│                          │
│  How was your sleep?     │
│       ★ ★ ★ ☆ ☆          │
│                          │
│  Notes (optional)        │
│  ┌──────────────────┐    │
│  │                  │    │
│  └──────────────────┘    │
│                          │
│  ┌──────────────────┐    │
│  │      Save        │    │
│  └──────────────────┘    │
└──────────────────────────┘
```

---

## W-08 – Trends

```
┌──────────────────────────┐
│  Trends      [Week▼]     │
│                          │
│  Sleep Duration          │
│  ┌────────────────────┐  │
│  │  ▄ ▄ █ ▄ █ ▄ ▄    │  │
│  │  M T W T F S S    │  │
│  └────────────────────┘  │
│                          │
│  Sleep Score             │
│  ┌────────────────────┐  │
│  │  ╱─╲   ╱─╲         │  │
│  │ ╱   ╲─╱   ╲        │  │
│  └────────────────────┘  │
│                          │
│  Avg Duration:  7h 10m   │
│  Avg Score:     74       │
│                          │
│  [Home] [Trends] [Tips] [⚙]│
└──────────────────────────┘
```

---

## Design Notes

- Primary color: Deep navy `#1A2340`
- Accent color: Soft teal `#4ECDC4`
- Background: Off-white `#F7F8FA` (light mode), Dark `#0D1117` (dark mode)
- Typography: Inter (headings), SF Pro / Roboto (body)
- All interactive elements must meet WCAG 2.1 AA contrast ratios.
- Detailed Figma files will be linked here once available.
