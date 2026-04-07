# User Flows – Sleep Naked

This document describes the primary user journeys through the Sleep Naked application.

---

## 1. Onboarding Flow

```
[App Launch]
     │
     ▼
[Splash Screen]
     │
     ▼
[Welcome Screen] ──► [Sign Up] ──► [Email & Password Entry]
                                          │
                                          ▼
                                   [Profile Setup]
                                   - Name
                                   - Age range
                                   - Sleep goal (hours)
                                   - Typical bedtime / wake time
                                          │
                                          ▼
                                   [Notification Permissions]
                                          │
                                          ▼
                                   [Home Dashboard]
```

**Alternate Path – Returning User:**
```
[App Launch] ──► [Login Screen] ──► [Home Dashboard]
```

---

## 2. Log Sleep Flow

```
[Home Dashboard]
     │
     ▼
[Tap "Log Sleep"]
     │
     ▼
[Sleep Entry Screen]
- Bedtime picker
- Wake time picker
- Quality rating (1–5 stars)
- Optional notes
     │
     ▼
[Save Entry]
     │
     ▼
[Sleep Score Display]
- Score (0–100)
- Key insight (e.g., "You slept 30 min less than your goal")
     │
     ▼
[Home Dashboard] (updated)
```

---

## 3. View Trends Flow

```
[Home Dashboard]
     │
     ▼
[Tap "Trends" tab]
     │
     ▼
[Trends Screen]
- Toggle: Week / Month / Year
- Chart: Sleep duration over time
- Chart: Sleep score over time
- Average stats summary
     │
     ▼
[Tap specific day/bar]
     │
     ▼
[Day Detail View]
- Full entry details
- Recommendations for that night
```

---

## 4. View Recommendations Flow

```
[Home Dashboard]
     │
     ▼
[Tap "Tips" / Recommendations card]
     │
     ▼
[Recommendations Screen]
- Personalized tip cards (based on recent data)
- Each card has: title, short description, "Learn More" link
     │
     ▼
[Tap "Learn More"]
     │
     ▼
[Tip Detail Screen]
- Full explanation
- Scientific backing (optional)
- "Mark as Done" / "Dismiss"
```

---

## 5. Settings & Account Flow

```
[Home Dashboard]
     │
     ▼
[Tap Profile / Settings icon]
     │
     ▼
[Settings Screen]
- Edit Profile
- Sleep Goal
- Notification Preferences
- Connected Devices (future)
- Privacy & Data
- Log Out
- Delete Account
```

---

## 6. Error States

| Scenario | Behavior |
|----------|----------|
| No internet on launch | Show cached data with offline banner |
| Invalid login credentials | Inline error message, offer password reset |
| Sleep log overlaps existing entry | Warning prompt: overwrite or cancel |
| Server error on save | Toast notification, retry option |

---

## Notes

- All primary actions should be reachable within **2 taps** from the Home Dashboard.
- The app should support swipe-back navigation on iOS and back-button navigation on Android.
