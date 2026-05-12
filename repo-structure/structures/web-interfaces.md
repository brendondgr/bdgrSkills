# Web Application Structure

This reference defines approved structures for website projects. Before creating files, the agent must use `website-architecture` to select one mode, define routes, map data flow, and document frontend/backend boundaries.

All website-specific code, assets, and runtime files live under the root `web/` directory. Repository documentation lives under `docs/`.

## Required Planning Files

Every website project must create or update:

- `docs/architecture.md`
- `docs/structure.md`
- `docs/routes.md`
- `docs/component-map.md`
- `docs/data-flow.md`
- `docs/deployment.md`
- `docs/api-contract.md` when backend/API contracts exist

## Mode A: Static Site

Use for portfolios, marketing pages, documentation sites, landing pages, and other non-authenticated informational sites.

```text
root/
├── docs/
├── web/
│   ├── pages/
│   ├── layouts/
│   ├── components/
│   ├── static/
│   │   ├── css/
│   │   ├── js/
│   │   └── images/
│   └── index.html
├── scripts/
└── README.md
```

## Mode B: Flask/Jinja Monolith

Use when Flask renders server-side templates directly.

```text
root/
├── docs/
├── web/
│   ├── app/
│   │   ├── __init__.py
│   │   ├── routes/
│   │   ├── services/
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── templates/
│   │   │   ├── base.html
│   │   │   ├── pages/
│   │   │   ├── layouts/
│   │   │   └── components/
│   │   └── static/
│   │       ├── css/
│   │       ├── js/
│   │       ├── images/
│   │       └── vendor/
├── tests/
├── scripts/
├── pyproject.toml
├── .env.example
└── README.md
```

## Mode C: Flask API + Frontend

Use when Flask owns API endpoints and a separate frontend owns rendering.

```text
root/
├── docs/
├── web/
│   ├── frontend/
│   │   ├── src/
│   │   │   ├── app/
│   │   │   ├── pages/
│   │   │   ├── layouts/
│   │   │   ├── components/
│   │   │   ├── features/
│   │   │   ├── lib/
│   │   │   ├── styles/
│   │   │   └── assets/
│   │   ├── public/
│   │   └── package.json
│   ├── backend/
│   │   ├── app/
│   │   │   ├── __init__.py
│   │   │   ├── routes/
│   │   │   ├── services/
│   │   │   ├── models/
│   │   │   ├── schemas/
│   │   │   ├── auth/
│   │   │   └── config.py
│   │   ├── tests/
│   │   └── pyproject.toml
│   └── shared/
│       └── contracts/
├── scripts/
├── .env.example
└── README.md
```

## Mode D: Django Application

Use when Django owns views, templates, apps, ORM, migrations, and admin behavior.

```text
root/
├── docs/
├── web/
│   ├── config/
│   │   ├── settings/
│   │   ├── urls.py
│   │   ├── asgi.py
│   │   └── wsgi.py
│   ├── apps/
│   │   └── <domain_app>/
│   │       ├── migrations/
│   │       ├── templates/
│   │       ├── static/
│   │       ├── models.py
│   │       ├── views.py
│   │       ├── urls.py
│   │       └── tests.py
│   ├── static/
│   └── templates/
├── scripts/
├── pyproject.toml
├── .env.example
└── README.md
```

## Mode E: Astro or React/Vite Frontend

Use when the project is primarily a frontend app or static pre-rendered site.

```text
root/
├── docs/
├── web/
│   ├── src/
│   │   ├── app/
│   │   ├── pages/
│   │   ├── layouts/
│   │   ├── components/
│   │   │   ├── ui/
│   │   │   ├── layout/
│   │   │   └── feature/
│   │   ├── features/
│   │   ├── lib/
│   │   ├── hooks/
│   │   ├── styles/
│   │   └── assets/
│   ├── public/
│   ├── package.json
│   └── vite.config.ts or astro.config.mjs
├── scripts/
└── README.md
```

## Mode F: Dockerized Web App

Use when local development, staging, or production must run through containers.

```text
root/
├── docs/
├── web/
│   ├── frontend/
│   ├── backend/
│   └── shared/
│       └── contracts/
├── infra/
│   ├── docker/
│   ├── nginx/
│   └── compose.yaml
├── scripts/
│   ├── dev.sh
│   ├── build.sh
│   └── test.sh
├── .env.example
└── README.md
```

## Ownership Guidelines

- Route/page views belong in `pages/` or framework-specific route files.
- Reusable visual pieces belong in `components/ui/`.
- Navigation, sidebars, footers, and app chrome belong in `components/layout/` or `layouts/`.
- Domain-specific UI belongs in `components/feature/` or `features/`.
- Server routes belong in backend route modules or framework URL/view files.
- API schemas, OpenAPI specs, and shared types belong in `shared/contracts/` when a frontend and backend both depend on them.
