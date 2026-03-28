---
name: Repository Structure Standard
description: Universal file structure and organization standards for repository consistency and maintainability.
---
# Repository Structure Standard

This document defines the universal file structure for all repositories within the ecosystem. Adhering to this structure ensures consistency, maintainability, and ease of navigation across different projects.

## Core Directory Structure

```text
root/
├── docs/       # Project documentation and architectural overviews
├── libs/       # Shared libraries and internal packages
├── utils/      # Utility functions and helper classes
└── web/        # Web application components and assets
```

---

## 1. Documentation (`docs/`)
All documentation regarding the project, including architecture, setup guides, and structural maps, resides here.

- **Mandatory File:** `docs/structure.md`
  - This file must be kept up-to-date with the current file structure.
  - It should detail main sub-folders and primary files, explaining their purpose without including source code.

---

## 2. Utilities (`utils/`)
Utilities that support the main codebase.

- **Small Utilities:** Basic utilities (e.g., a simple logger) should be kept as individual files directly within `utils/`.
- **Large Utilities:** If a utility requires complex logic or becomes a large class, it should be placed in its own sub-folder.
- **Initialization:** For Python projects, sub-folders must include an `__init__.py` file for proper package initialization.

---

## 3. Web Components (`web/`)
The `web/` directory handles all web-based items and follows a highly templatized hierarchy.

```text
web/
├── static/
│   ├── css/    # Categorized CSS files
│   └── js/     # Categorized JavaScript files
├── images/     # Assets (SVG and standard formats)
└── templates/  # HTML templates
```

- **Templates:** Main `.html` pages are placed directly inside `templates/`.
- **Parts/Components:** Any HTML fragments or partials that build upon the main pages should be stored in sub-directories named after the parent page.

---

## 4. Libraries (`libs/`)
Internal libraries and external-facing components are modularized within the `libs/` directory.

---

## Code Guidelines

### File Length Limits
- **Maximum Length:** 800 lines.
- **Ideal Length:** Under 500 lines.
- **Rule:** Favor modularity. If a file exceeds 800 lines, outsource logic to secondary files/modules.

### Package Management
We use `uv` as the primary package manager for all projects.
- **Primary Commands:** `uv add`, `uv init`, `uv run`.
- Avoid using other package managers unless explicitly required by environment constraints.

---

## Examples

### Utility Organization (`utils/`)

- **Single Functionality:**
  - `utils/logger.py` – A lightweight logging class.
- **Complex Sub-system:**
  - `utils/auth_handler/`
    - `__init__.py` – Orchestrates the authentication exports.
    - `oauth.py` – Handles OAuth2 flows.
    - `session.py` – Manages user sessions.

### Web Template Organization (`web/templates/`)

- **Main Page:** `web/templates/dashboard.html`
- **Dashboad Fragments:**
  - `web/templates/dashboard/nav.html`
  - `web/templates/dashboard/sidebar.html`
  - `web/templates/dashboard/charts.html`

### Directory Summary Table (Sample `docs/structure.md` entry)

| File / Folder | Purpose |
| :--- | :--- |
| `web/templates/index.html` | The primary entry point for the landing page. |
| `web/templates/index/hero.html` | The hero section component for the landing page. |
| `utils/database.py` | Minimal database connection wrapper. |
| `utils/payment_engine/` | Sub-folder for complex transaction logic. |

---

*Last Updated: 2026-02-28*
