# Layout, Geometry & Glassmorphism

Unexpected layouts, generous negative space or controlled density.

### Geometry
- **Border Radii**: Generous rounding (`6px` to `24px`).
- **Elevation**: Deep, diffuse drop-shadows for spatial hierarchy.
- **Backgrounds**: Noise textures, grain overlays, or subtle meshes.

### Glassmorphism System
Layering depth suitable for dark mode:
- Semi-transparent overlays.
- Backdrop blurs to allow content to softly bleed through.

### Implementation Example
```html
<!-- UnoCSS Glassmorphism Card -->
<div class="bg-black/40 backdrop-blur-md rounded-xl shadow-2xl border border-white/10">
  Content here
</div>
```
