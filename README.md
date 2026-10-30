# 🚗 FleetPilot — Intelligent Fleet Management System

> A full-stack MEAN application for real-time fleet tracking, route optimisation, driver management, fuel & expense analytics, and automated maintenance scheduling.

---

## Tech Stack

| Layer      | Technology                                      |
|------------|-------------------------------------------------|
| Frontend   | Angular 17+ (standalone components, lazy routes, TypeScript) |
| Backend    | Node.js · Express 5 · Mongoose (MongoDB)        |
| Auth       | JWT (access + refresh tokens) · bcrypt          |
| Real-time  | Socket.IO (vehicle location, notifications)     |
| Maps       | Leaflet / Google Maps API                       |
| Testing    | Jest · Supertest                                |

---

## Team & Module Ownership

| Member   | Feature Modules                                              | Backend paths                                                                         | Frontend paths                                              |
|----------|--------------------------------------------------------------|---------------------------------------------------------------------------------------|-------------------------------------------------------------|
| **Member 1** | **Real-Time Tracking & Route Optimisation**             | `backend/src/modules/tracking/`<br>`backend/src/modules/routes-optimization/`        | `features/tracking/`<br>`features/route-planner/`           |
| **Member 2** | **Vehicle & Driver Management**                         | `backend/src/modules/vehicles/`<br>`backend/src/modules/drivers/`                    | `features/vehicles/`<br>`features/drivers/`                 |
| **Member 3** | **Fuel & Expense Tracking, Analytics & Dashboard**      | `backend/src/modules/fuel-expense/`<br>`backend/src/modules/analytics/`              | `features/fuel-expense/`<br>`features/analytics/`<br>`features/dashboard/` |
| **Member 4** | **Auth, Trips, Maintenance & Notifications (+ Admin)**  | `backend/src/modules/auth/`<br>`backend/src/modules/trips/`<br>`backend/src/modules/maintenance/`<br>`backend/src/modules/notifications/` | `features/auth/`<br>`features/trips/`<br>`features/maintenance/`<br>`features/notifications/`<br>`features/admin/` |

---

## Project Structure (overview)

```
fleetpilot/
├── backend/
│   ├── src/
│   │   ├── config/               # DB connection & env validation
│   │   ├── middleware/            # Auth, role, error middleware
│   │   ├── utils/                 # Logger, API response helpers
│   │   ├── modules/               # Feature modules (routes · controllers · models)
│   │   │   ├── auth/              # Member 4
│   │   │   ├── tracking/          # Member 1
│   │   │   ├── routes-optimization/ # Member 1
│   │   │   ├── vehicles/          # Member 2
│   │   │   ├── drivers/           # Member 2
│   │   │   ├── fuel-expense/      # Member 3
│   │   │   ├── analytics/         # Member 3
│   │   │   ├── trips/             # Member 4
│   │   │   ├── maintenance/       # Member 4
│   │   │   └── notifications/     # Member 4
│   │   ├── app.js
│   │   └── server.js
│   ├── tests/                     # Per-module test suites
│   ├── .env.example
│   └── package.json
│
├── frontend/
│   └── src/app/
│       ├── core/                  # Services, guards, interceptors, models
│       ├── shared/                # Reusable components, pipes, directives
│       ├── layout/                # Navbar, sidebar, footer
│       └── features/              # Lazy-loaded feature modules (per member above)
│
├── docs/
│   ├── architecture.md
│   ├── api-docs.md
│   └── db-schema.md
└── README.md
```

---

## Getting Started

### Backend
```bash
cd backend
cp .env.example .env        # fill in MONGO_URI, JWT_SECRET, PORT
npm install
npm run dev
```

### Frontend
```bash
cd frontend
npm install
ng serve
```

---

## Documentation

| Doc | Description |
|-----|-------------|
| `docs/architecture.md` | System overview, component diagram, data-flow |
| `docs/api-docs.md` | REST endpoint reference with request/response schemas |
| `docs/db-schema.md` | MongoDB collections, Mongoose models, ERD |

---

## Conventions

- **Branch naming**: `feat/<module>/<short-description>` (e.g. `feat/tracking/geofence-alerts`)
- **Commit style**: [Conventional Commits](https://www.conventionalcommits.org/) (`feat:`, `fix:`, `chore:`)
- **PR rule**: Each PR must be reviewed by at least one other team member before merge to `main`
- **API contract**: All responses follow the `apiResponse` helper envelope `{ success, data, message }`
