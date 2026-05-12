# Website Architecture Setup

Before creating or modifying a website, dashboard, or web application, answer these questions and use the answers to create the architecture planning artifact.

## 1. Application Type

Which primary mode should this project use?

- Static informational site
- Flask/Jinja monolith
- Flask API + separate frontend
- Django application
- Astro site
- React/Vite frontend
- Dashboard/admin panel
- Dockerized full-stack app

## 2. User Roles

Which user roles exist?

- Public users
- Logged-in users
- Admin users
- Internal or high-permission users

For each role, define what routes and actions it can access.

## 3. Route Map

List every major route or page before building. For each route, define:

- path
- purpose
- required auth level
- data dependencies
- primary page/layout/components
- backend endpoints used, if any

## 4. Data Sources and Flow

Define where data comes from and how it reaches the UI:

- static content
- database records
- uploaded files
- third-party APIs
- server-rendered context
- client-side state only
- cached or derived data

## 5. Backend and API Needs

If a backend or API exists, define:

- framework
- endpoint groups
- request/response contracts
- validation ownership
- error response shape
- shared schema location

If no backend exists, explicitly state that `docs/api-contract.md` is not required.

## 6. Auth and Session Requirements

Define:

- auth mechanism, if any
- session or token ownership
- protected route behavior
- logged-out redirects or fallback states
- admin/high-permission boundaries

## 7. Runtime and Deployment

Define:

- local dev command
- build command
- test command
- deployment target
- required environment variables
- whether Docker is required

## 8. Testing and Validation

Define which checks are required:

- frontend unit/component tests
- backend tests
- route/API tests
- accessibility checks
- responsive viewport checks
- lint and format checks
- production build check

## Required Planning Artifact

Before Step 5 of `initialize.md`, summarize the answers into a short planning artifact that names the selected application mode, routes, auth roles, data flow, repository layout, docs to create, and commands to run.
