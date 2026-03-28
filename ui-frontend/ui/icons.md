# Icons System

Icons form a core part of the brand identity. Keep stroke widths consistent across all viewports. Touch targets must be enlarged on mobile without increasing the visual footprint of the icon itself.

### Functional Mapping
- **Primary Actions**: Brand primary colors.
- **Edit/Manage**: Muted secondary tones.
- **Success/Create**: Bright positive tones.
- **Danger**: High-alert colors.

### Implementation Structure (UnoCSS/Tailwind)

```html
<!-- Mobile-friendly Interactive Icon button -->
<button class="p-3 sm:p-2 -m-3 sm:-m-2 rounded-full hover:bg-white/10 active:bg-white/20 transition-colors group" aria-label="Settings">
  <!-- The padding/margin trick ensures a 44x44px hit bounds on mobile while looking like 24x24px visually -->
  <svg class="w-6 h-6 text-gray-400 group-hover:text-primary transition-colors" fill="none" viewBox="0 0 24 24" stroke="currentColor">
    <!-- Icon paths -->
  </svg>
</button>
```
