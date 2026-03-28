# Web Interface Structure

The `web/` directory handles all web-based application components and adheres to a highly templatized hierarchy. This structure ensures clear separation between assets, templates, and component fragments.

## Directory Layout

```text
web/
├── static/
│   ├── css/    # Categorized CSS files (e.g., UnoCSS variables, custom styles)
│   └── js/     # Categorized JavaScript files (e.g., client logic, GSAP animations)
├── images/     # Assets (SVG, PNG, WebP)
└── templates/  # Main HTML templates and isolated components
```

## Components & Templates Guidelines

- **Main Templates:** Core page views (e.g., `.html` files) operate as the entry points and are placed directly inside `templates/`.
- **Parts/Components:** Any HTML fragments or partials that build upon the main pages must be stored in sub-directories named exactly after the parent page.

### Example Organization

```text
web/templates/
├── index.html                   # Main Landing Page
├── index/                       # Components exclusive to index.html
│   ├── hero.html
│   ├── features.html
│   └── footer.html
├── dashboard.html               # Main Dashboard Page
└── dashboard/                   # Components exclusive to dashboard.html
    ├── nav.html
    ├── sidebar.html
    └── charts.html
```

### Purpose Table Example

| File / Folder | Purpose |
| :--- | :--- |
| `web/templates/index.html` | The primary entry point for the landing page. |
| `web/templates/index/hero.html` | The hero section component for the landing page. |
