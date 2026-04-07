# Architecture

## High-Level Overview

```
┌─────────────┐     HTTPS/REST     ┌──────────────────┐
│  Mobile App │ ◄──────────────── ▶│  Backend API      │
│  (React     │                    │  (Node.js /       │
│   Native)   │                    │   Express)        │
└─────────────┘                    └────────┬─────────┘
                                            │
┌─────────────┐     HTTPS/REST             │ ORM
│  Web App    │ ◄──────────────── ▶        │
│  (React)    │                    ┌────────▼─────────┐
└─────────────┘                    │  Database        │
                                   │  (PostgreSQL)    │
                                   └──────────────────┘
```

## Components

### Mobile App (`app/mobile/`)
- **Framework**: React Native
- **State management**: Redux Toolkit
- **Navigation**: React Navigation

### Web App (`app/web/`)
- **Framework**: React (Vite)
- **State management**: Redux Toolkit
- **Routing**: React Router

### Backend API (`backend/`)
- **Runtime**: Node.js
- **Framework**: Express
- **ORM**: Prisma
- **Auth**: JWT + refresh tokens

### Database
- **Engine**: PostgreSQL
- **Migrations**: Prisma Migrate

## Key Design Decisions

- Shared business logic lives in the backend; clients are thin.
- All API responses follow a standard `{ data, error, meta }` envelope.
- Sensitive user data is encrypted at rest.
