# Colors & Themes

The application uses a carefully curated dark-mode color system. All color implementations must be responsive and adapt to different screen contexts while maintaining high contrast.

### Neutral Base
- **Background**: `#0a0a0a` (Deep Matte Black) — Provides a stark, high-contrast canvas.
- **Surface**: `#141414` (Dark Gray) — Used for cards and secondary panels.
- **Elevated**: `#1e1e1e` (Lighter Gray) — Used for modals, dropdowns, and floating elements.

### Brand Colors
- **Primary**: Neon or vibrant highlights for main buttons and primary actions.
- **Secondary**: Muted cool tones for navigation, info states.
- **Tertiary**: Bright success and dynamic accents.
- **Danger**: High-visibility alert reds for destructive actions.

### Categorization Tones
Used for classifying various data types:
1. **Deep Background**: Very low opacity, dark-tinted backgrounds.
2. **Vibrant Border**: Bright, saturated borders for categorization.
3. **High-contrast Text**: Light, bright text for legibility.

### Implementation Structure (UnoCSS/Tailwind)
```css
/* variables.css */
:root {
  --color-bg-base: #0a0a0a;
  --color-surface: #141414;
  --color-elevated: #1e1e1e;
  --color-primary: 39, 214, 163; /* RGB for opacity usage */
}
```

```html
<!-- Mobile-friendly card with surface color and vibrant border hover -->
<div class="bg-[var(--color-surface)] sm:bg-transparent sm:hover:bg-[var(--color-surface)] border border-transparent hover:border-[rgba(var(--color-primary),0.5)] transition-colors rounded-xl p-4 w-full max-w-sm">
  <span class="text-[rgba(var(--color-primary),1)] font-semibold text-sm">Category Label</span>
</div>
```
