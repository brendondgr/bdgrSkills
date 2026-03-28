# Layout, Geometry & Glassmorphism

The app makes extensive use of transparency, depth, and soft geometry to feel layered. Mobile-first design is critical.

### Soft Geometry
- **Border Radii**: Generous rounding (`6px` to `24px`). Modals and segmented controls use high radii to soften the technical nature.
- **Elevation**: A shadow system using deep, diffuse drop-shadows creates clear spatial hierarchy.

### Modular Glassmorphism
- **Backdrop Blur**: Semi-transparent dark overlays with `backdrop-filter: blur()`.
- **Themed Glows**: Interactive elements use vibrant neon glows on hover (adapt to touch states on mobile).

### Mobile-First Layout Strategy
- **Dynamic Layouts**: Minimum widths enforced with horizontal scrolling to maintain legibility on narrow screens.
- **Component Swapping**: Small icon-only variants replace labelled components on smaller screens.

### Implementation Structure (UnoCSS/Tailwind & React)

```html
<!-- Glassmorphism Container with Mobile Padding -->
<div class="bg-black/40 backdrop-blur-xl rounded-2xl sm:rounded-3xl shadow-2xl border border-white/5 p-4 sm:p-6 md:p-8 w-full overflow-hidden">
  <!-- Content -->
</div>
```

```html
<!-- Horizontal scrolling container for mobile data density -->
<div class="flex overflow-x-auto snap-x snap-mandatory pb-4 -mx-4 px-4 sm:mx-0 sm:px-0 scrollbar-hide">
  <div class="snap-start shrink-0 w-[85vw] sm:w-auto">
    <!-- Card Content -->
  </div>
</div>
```
