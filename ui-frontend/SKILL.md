---
trigger: model_decision
description: Use this skill when the user asks to build web components, pages, artifacts, posters, or applications. Generates creative, polished code and UI design that avoids generic AI aesthetics.
---

# Frontend Design & UI System

**CRITICAL REQUIREMENT**: The user MUST specify which technology stack to use for implementation. You must actively confirm the requested stack if it is not provided. Supported technologies include:
- **Astro**
- **UnoCSS**
- **Tailwind**
- **GSAP**
- **React**

This system guides the creation of distinctive, production-grade interfaces. It embraces high-contrast, dark-mode aesthetics with intentional design choices, heavily optimized for mobile-first responsiveness.

## Core Principles
- **Purpose & Tone**: Choose a bold, memorable direction (maximalist chaos, raw brutalism, refined minimalism, etc.).
- **Execution**: Meticulous details, no overused fonts (Inter/Roboto), and avoiding generic purple gradients or predictable layouts.
- **ADA Compliance & Accessibility**: All designs must explicitly adhere to WCAG 2.2 AA standards (e.g., minimum contrast of 4.5:1 for text, 3:1 for non-text UI, visible focus indicators, and semantic HTML). Screen reader support via VoiceOver and TalkBack should be continuously validated.
- **Mobile-First & Readability**: You must include `<meta name="viewport" content="width=device-width, initial-scale=1">` in the HTML heads. Enforce large, legible text (minimum 16px body on mobile) utilizing fluid type `clamp()` strategies, generous tap spacing, and touch-target minimums (44x44px). No layout should ever force horizontal-scrolling on a 320px viewport. 
- **SEO & Rendering Parity**: Mobile and desktop structural parity must be maintained for Google Mobile-First Indexing via flexible CSS grids (`fr`, `%`), identical structured data, and non-blocking CSS/JS.

## Component & Asset Index
- [Colors & Themes](ui/colors.md)
- [Typography](ui/typography.md)
- [Layout & Geometry](ui/geometry.md)
- [Motion & Animations](ui/motion.md)
- [Buttons & Interactive Elements](ui/buttons.md)
- [Dropdowns & Selects](ui/dropdowns.md)
- [Modals & Popups](ui/modals.md)
- [Icons System](ui/icons.md)
- [Data Visualization & Graphs](ui/data-viz.md)
