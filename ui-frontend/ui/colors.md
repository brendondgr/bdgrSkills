# Colors & Themes

The application uses a carefully curated dark-mode color system. All color implementations must be responsive and adapt to different screen contexts while maintaining high contrast.

### Neutral Base
- **Background**: `#0a0a0a` (Deep Matte Black) — Provides a stark, high-contrast canvas.
- **Surface**: `#141414` (Dark Gray) — Used for cards and secondary panels.
- **Elevated**: `#1e1e1e` (Lighter Gray) — Used for modals, dropdowns, and floating elements.

### Brand Colors (Neon & Vibrant)
The interface relies on high-energy, neon colors to pop against the dark matte backgrounds. These must be used intentionally to create "glow" effects and draw focus.

Select from this extended neon palette when defining your application's unique signature (use RGB values for opacity manipulation via CSS variables):
- **Cyber Cyan**: `#00f0ff` | `0, 240, 255` — Excellent for primary interactive elements and futuristic tech styling.
- **Toxic Green**: `#39ff14` | `57, 255, 20` — High-contrast success states or hyper-visible calls to action.
- **Matrix Mint**: `#00ff9d` | `0, 255, 157` — Slightly softer neon green, ideal for primary branding.
- **Plasma Pink**: `#ff007f` | `255, 0, 127` — Bold accents, active states, or intense notification dots.
- **Hot Magenta**: `#d500ff` | `213, 0, 255` — Deep but vibrant, great for dark glows paired with cyan or pink.
- **Electric Violet**: `#7000ff` | `112, 0, 255` — Secondary cool tones that maintain a luminescent quality.
- **Atomic Orange**: `#ff5500` | `255, 85, 0` — Warnings, secondary actions, or energetic highlights.
- **Laser Lemon**: `#eaff00` | `234, 255, 0` — Badges, prominent warnings, or extreme contrast text on dark backgrounds.
- **Neon Crimson (Danger)**: `#ff003c` | `255, 0, 60` — High-visibility alert reds for destructive actions and critical errors.

### Categorization Tones
Used for classifying various data types:
1. **Deep Background**: Very low opacity, dark-tinted backgrounds (e.g., `rgba(0, 255, 157, 0.05)`).
2. **Vibrant Border**: Bright, saturated borders for categorization (e.g., 1px solid `#00ff9d`).
3. **High-contrast Text**: Light, bright text for legibility.

### Implementation Structure (UnoCSS/Tailwind)
```css
/* variables.css */
:root {
  --color-bg-base: #0a0a0a;
  --color-surface: #141414;
  --color-elevated: #1e1e1e;
  
  /* Neon Brand Tokens - RGB defined for opacity modifications */
  --color-primary: 0, 255, 157;    /* #00ff9d */
  --color-secondary: 59, 130, 246; /* #3b82f6 */
  --color-tertiary: 255, 0, 127;   /* #ff007f */
  --color-danger: 255, 0, 60;      /* #ff003c */
}
```

```html
<!-- Mobile-friendly card with surface color and vibrant border hover -->
<div class="bg-[var(--color-surface)] sm:bg-transparent sm:hover:bg-[var(--color-surface)] border border-transparent hover:border-[rgba(var(--color-primary),0.5)] transition-colors rounded-xl p-4 w-full max-w-sm">
  <span class="text-[rgba(var(--color-primary),1)] font-semibold text-sm">Category Label</span>
</div>
```
