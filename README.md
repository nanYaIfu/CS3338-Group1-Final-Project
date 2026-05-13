# Campus Resource Booking & Check-In System

**CS3338 — Group 1 Final Project**

> A full-stack web platform for students to browse, book, and check in to campus resources (study rooms, labs, tutoring sessions). Staff manage resources; admins view usage analytics.

---

## Jira Project Board

🔗 **[View our Jira board](https://calstatela-team-fxcoefw5.atlassian.net/jira/software/projects/WT/boards/101)**


---

## Why This Project Matters

Campus resources like study rooms and computer labs are in high demand but are typically managed informally — paper sign-ups, email chains, or untracked walk-ins. Students waste time visiting occupied spaces, no-shows block available slots, and staff have no usage data. This system solves that with a clean, role-aware platform that handles the full booking lifecycle.

---

## Tech Stack

| Layer     | Technology                                          |
|-----------|-----------------------------------------------------|
| Frontend  | React 18, React Router 6, Axios, Bootstrap 5, recharts |
| Backend   | Node.js 18, Express.js 4, REST API                  |
| Auth      | JWT (jsonwebtoken), bcrypt, express-rate-limit      |
| Validation| express-validator                                   |
| Database  | MongoDB 6, Mongoose 7                               |
| DevOps    | Docker, docker-compose, GitHub                      |

---

## Team Roles

|Name         | Role           | Responsibility                                               |
|-------------|----------------|--------------------------------------------------------------|
| I. Okafor   | Project Lead   | Planning, Jira, professor communication, documentation       |
| B. Rodriguez| Backend Dev 1  | Auth & Users — register, login, JWT, RBAC middleware         |
| H. Dsouza   | Backend Dev 2  | Resources & Booking — CRUD, conflict detection, analytics    |
| I. Melchor  | Frontend Dev   | All React pages, API integration, UI/UX                      |
| N. Uribe    | DevOps / QA    | Docker, TestRail, workflow diagram, seed data                |

---

## Repository Structure

```
campus-resource-booking-checkin/
├── frontend/          # React 18 SPA
├── backend/           # Node.js + Express API
├── docs/              # All LaTeX documents
│   ├── sdd.tex
│   ├── srs.tex
│   ├── user_manual.tex
│   ├── design_spec.tex
│   ├── snapshot_objectives.tex
│   ├── workflow_diagram.tex
│   └── testrail/
├── docker-compose.yml
└── README.md
```

---

## How to Run

### With Docker (Recommended)

```bash
git clone https://github.com/nanYaIfu/CS3338-Group1-Final-Project.git
cd CS3338-Group1-Final-Project/campus-resource-booking-checkin

cp backend/.env.example backend/.env

docker-compose up --build
```

| Service  | URL                       |
|----------|---------------------------|
| Frontend | http://localhost:3000     |
| API      | http://localhost:5000     |
| MongoDB  | localhost:27017           |


### Without Docker

```bash
# Terminal 1 — Backend
cd backend && npm install && npm run dev

# Terminal 2 — Frontend
cd frontend && npm install && npm start
```

Requires MongoDB running on `localhost:27017` (or set `MONGO_URI` in `.env` to a MongoDB Atlas URL).

---

## Seed Accounts

| Role    | Email                | Password   |
|---------|----------------------|------------|
| Admin   | admin@campus.edu     | admin123   |
| Staff   | staff@campus.edu     | staff123   |
| Student | student@campus.edu   | student123 |

> ⚠️ Change all seed passwords before any public deployment.

---

## Snapshot Progress

| Snapshot   | Date         | Focus                                          | Status      |
|------------|--------------|------------------------------------------------|-------------|
| Snapshot 1 | Feb 2, 2025  | Foundation, docs, Docker, workflow diagram     | ✅ Complete |
| Snapshot 2 | Mar 2, 2025  | Auth, resource CRUD, booking flow              | ✅ Complete |
| Snapshot 3 | Apr 6, 2025  | Check-in system, admin dashboard, analytics    | ✅ Complete |
| Snapshot 4 | May 15, 2025 | Polish, bug fixes, rate limiting, final docs   | ✅ Complete |
