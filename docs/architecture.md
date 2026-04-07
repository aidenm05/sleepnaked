# Architecture – Sleep Naked

## Overview

Sleep Naked follows a client–server architecture with separate mobile and web front-ends communicating with a shared backend API. The system is designed for scalability, privacy, and a smooth developer experience.

---

## High-Level Architecture

```
┌─────────────────────────────────────────────────────┐
│                   Clients                           │
│  ┌──────────────────┐   ┌──────────────────────┐   │
│  │   Mobile App     │   │      Web App         │   │
│  │  (React Native)  │   │     (React/Next.js)  │   │
│  └────────┬─────────┘   └──────────┬───────────┘   │
└───────────┼──────────────────────── ┼───────────────┘
            │          HTTPS / REST   │
            ▼                         ▼
┌─────────────────────────────────────────────────────┐
│                   Backend API                       │
│             (Node.js / Express or FastAPI)          │
│  ┌──────────┐  ┌──────────────┐  ┌──────────────┐  │
│  │  Auth    │  │ Sleep Logs   │  │ Recommend-   │  │
│  │  Service │  │   Service    │  │ ations Svc   │  │
│  └──────────┘  └──────┬───────┘  └──────────────┘  │
└─────────────────────── ┼───────────────────────────┘
                         │
            ┌────────────┼────────────┐
            ▼            ▼            ▼
      ┌──────────┐ ┌──────────┐ ┌──────────┐
      │ Primary  │ │  Cache   │ │  Object  │
      │    DB    │ │ (Redis)  │ │ Storage  │
      │(PostgreSQL│ └──────────┘ │  (S3)   │
      └──────────┘               └──────────┘
```

---

## Technology Stack

### Mobile (app/mobile/)

| Component | Technology |
|-----------|------------|
| Framework | React Native (Expo) |
| Language | TypeScript |
| State Management | Zustand |
| Navigation | React Navigation |
| HTTP Client | Axios |
| Local Storage | AsyncStorage |
| Charts | Victory Native |

### Web (app/web/)

| Component | Technology |
|-----------|------------|
| Framework | Next.js 14 |
| Language | TypeScript |
| Styling | Tailwind CSS |
| State Management | Zustand |
| HTTP Client | Axios |
| Charts | Recharts |

### Backend (backend/)

| Component | Technology |
|-----------|------------|
| Runtime | Node.js 20 LTS |
| Framework | Express.js |
| Language | TypeScript |
| ORM | Prisma |
| Database | PostgreSQL 15 |
| Cache | Redis |
| Auth | JWT + refresh tokens |
| Validation | Zod |

### Infrastructure

| Component | Technology |
|-----------|------------|
| Cloud | AWS |
| Container | Docker + ECS |
| CI/CD | GitHub Actions |
| Monitoring | Datadog |
| Error Tracking | Sentry |

---

## Data Models

### User

```typescript
interface User {
  id: string;           // UUID
  email: string;
  name: string;
  ageRange: string;
  sleepGoalHours: number;
  targetBedtime: string; // HH:MM
  targetWakeTime: string; // HH:MM
  createdAt: Date;
  updatedAt: Date;
}
```

### SleepLog

```typescript
interface SleepLog {
  id: string;           // UUID
  userId: string;
  bedtime: Date;
  wakeTime: Date;
  durationMinutes: number;
  qualityRating: number; // 1–5
  notes?: string;
  sleepScore: number;    // 0–100 (computed)
  createdAt: Date;
}
```

---

## API Design

The backend exposes a RESTful API at `/api/v1`.

### Endpoints (MVP)

| Method | Path | Description |
|--------|------|-------------|
| POST | `/auth/register` | Register new user |
| POST | `/auth/login` | Authenticate user |
| POST | `/auth/refresh` | Refresh access token |
| GET | `/users/me` | Get current user profile |
| PATCH | `/users/me` | Update user profile |
| GET | `/sleep-logs` | List sleep logs (paginated) |
| POST | `/sleep-logs` | Create a new sleep log |
| GET | `/sleep-logs/:id` | Get a specific sleep log |
| DELETE | `/sleep-logs/:id` | Delete a sleep log |
| GET | `/recommendations` | Get personalized recommendations |

---

## Security

- All traffic over HTTPS (TLS 1.2+).
- Passwords hashed with bcrypt (cost factor 12).
- JWT access tokens expire in 15 minutes; refresh tokens in 30 days.
- Sleep data encrypted at rest (AES-256).
- Rate limiting on all public endpoints.
- GDPR: users can export and delete all their data.

---

## Scalability Considerations

- Stateless API allows horizontal scaling behind a load balancer.
- Redis caches frequently requested recommendations and trend aggregations.
- Database read replicas for analytics queries.
- Background jobs (e.g., score computation, notification scheduling) handled via a task queue (BullMQ).
