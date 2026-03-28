---
name: User Interface & Design System
description: Guidelines and technology stack for building modern, premium, dark-themed user interfaces using UnoCSS and GSAP.
---
# User Interface & Design System

This document outlines the design system used across the application. The interface is designed to be modern, high-energy, and premium, balancing functional data density with a sleek, dark-themed aesthetic.

## 🛠️ Technology Stack

The styling and animation of the application are powered by:

- **UnoCSS**: Used as the primary utility-first CSS engine. All styling should leverage UnoCSS atomic utility classes for consistency, rapid development, and minimal CSS footprint.
- **GSAP (GreenSock Animation Platform)**: Used for all complex, programmatic animations and transitions across the interface.

---
## 🎨 Color Palette

The application uses a carefully curated dark-mode color system defined in `variables.css`.

### Brand Colors

- **Primary:** Neon or vibrant highlights for main buttons and primary actions.
- **Secondary:** Muted cool tones for navigation, info states, and secondary focus.
- **Tertiary:** Bright success and dynamic accents.

### Neutral Base

- **Background:** `#0a0a0a` (Deep Matte Black) — Provides a stark, high-contrast canvas.
- **Surface:** `#141414` (Dark Gray) — Used for cards and secondary panels to stand out slightly from the background.
- **Elevated:** `#1e1e1e` (Lighter Gray) — Used for modals, dropdowns, and floating elements.

### Categorization Tones

The application features predefined color sets used for classifying various data types or categories. Each category follows a consistent dark-theme implementation:

1.  **Deep Background:** Very low opacity, dark-tinted backgrounds for the main container area.
2.  **Vibrant Border:** Bright, saturated borders for clear visual categorization against dark backgrounds.
3.  **High-contrast Text:** Light, bright text for maximum legibility.

---

## ✨ Design Philosophy & Style Choices

### 1. Modern Typography

- **Headings:** Geometric and modern typefaces that provide a sleek, functional personality.
- **Body:** Clean sans-serif aesthetics chosen for high legibility in information-dense views.
- **Mono:** Monospaced fonts used for labels, numerical values, and metadata to emphasize the data-driven focus.

### 2. Modular Glassmorphism

The app makes extensive use of transparency and depth to feel "layered", specifically adapted for a dark mode environment:

- **Glass headers:** Uses backdrop filters (`blur`) with semi-transparent dark overlays to allow underlying content to softly show through.
- **Themed Glows:** Interactive elements use vibrant neon glows on hover, making the dark UI feel "alive."

### 3. Soft Geometry

- **Border Radii:** Generous rounding is applied throughout (`6px` to `24px`). Modals and segmented controls use high radii to soften the technical nature of the grid.
- **Elevation:** A shadow system using deep, diffuse drop-shadows creates clear spatial hierarchy for overlapping components.

### 4. Interactive Fidelity & GSAP Animations

Interactive elements and fluid motions are essential to the design system. **GSAP** is the standard for managing these animations correctly:

- **Micro-animations:** Segmented controls and toggles use GSAP's equivalent "spring" easings (`CustomEase` or `elastic`) for a snappy, responsive feel.
- **Interactive Cards:** Component cards feature a hover lift effect and a slight scale up to provide immediate feedback.
- **Loading & On-Screen Animations:** Care must be taken so GSAP animations are triggered at the correct points:
  - **Fade-in animations** should always animate to `opacity: 1` (`100%`).
  - **Elements that start on screen** (already within the viewport on initial load) must have `100%` opacity immediately. Do not delay their visibility.
  - **Elements entering the screen** differently (e.g., scrolled into view or loaded dynamically) should appear gracefully (fade/slide in) as the user loads them in.

---

## 🖼️ SVG Icon System

Icons are treated as part of the brand identity and use functional color mappings appropriate for a dark theme:

- **Primary Actions:** Brand primary vibrant colors.
- **Management/Edit:** Muted or secondary brand dark/cool colors.
- **Creation/Success:** Bright, positive tones.
- **Danger/Destruction:** High-visibility alert colors (e.g., intense reds).

---

## 📱 Responsive Strategy

The design uses a mobile-first approach:

- **Dynamic Layouts:** Complex structures persist across breakpoints, but container minimum widths are enforced with horizontal scrolling to maintain legibility.
- **Component Swapping:** Small icon-only variants replace labelled components on smaller screens to preserve space.
- **Responsive Sizing:** CSS variables are manipulated to adjust interface density based on device width.

---

## 🧭 Interaction Patterns

### 1. In-App Popups & Modals

To maintain a premium experience, browser-native dialogs are actively discouraged.

- **Custom Components**: All user confirmations, errors, and inputs should use custom in-app modal components.
- **Glassmorphism Backdrop**: Modals should appear over a blurred, dark semi-transparent overlay to maintain context while focusing the user's attention.
- **Spring Entrance**: Modals should animate in using the brand's spring curves for a tactile feel.
- **Destructive Actions**: Confirmation for destructive actions (like deleting an item/entry) must clearly use the brand's danger/alert color for primary confirmation buttons.
