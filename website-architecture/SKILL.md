---
name: website-architecture
description: Use this skill when planning, scaffolding, restructuring, or documenting a website, dashboard, web app, Flask app, Django app, Astro site, React frontend, or Dockerized web application.
---

# Website Architecture Skill

This skill defines the structural phase that must happen before UI code is generated for a website or web application. It sits between universal repository structure and frontend visual implementation.

## Required Outputs

Before generating website files, define:

1. Application mode
2. Route map
3. User role and auth map
4. Data-flow map
5. Frontend/backend boundary
6. Directory structure
7. Required documentation files
8. Build, run, and test commands

## Core Rule

Do not generate isolated visual pages until structure, routes, and data flow are defined.

## Application Modes

Choose exactly one primary mode before scaffolding:

- Static site
- Flask/Jinja monolith
- Flask API + separate frontend
- Django application
- Astro site
- React/Vite frontend
- Dashboard or admin panel
- Dockerized full-stack app

If a project combines modes, name the primary mode and document the secondary mode in `docs/architecture.md`.

## Route Map

Every major route or page must be listed before implementation. For each route, define:

- path
- purpose
- user role or auth level
- data dependencies
- primary page/layout/component ownership
- backend endpoints used, if any

## Data Flow

Document where data comes from and how it moves through the application:

- static content
- database-backed content
- uploaded files
- third-party APIs
- server-rendered data
- client-only state
- cached or derived data

## Frontend/Backend Boundary

For projects with both frontend and backend code, define:

- which layer owns routing
- which layer owns auth/session handling
- which layer validates data
- which endpoints or contracts connect the layers
- where shared schemas or API specs live

## Required Documentation

Create or update:

- `docs/architecture.md`
- `docs/structure.md`
- `docs/routes.md`
- `docs/component-map.md`
- `docs/data-flow.md`
- `docs/deployment.md`
- `docs/api-contract.md` when backend/API contracts exist

Each document should be concise, concrete, and useful for a later agent or engineer maintaining the project.
