# Typography

Typography must be legible on both small mobile screens and large desktop displays.

### Core Choices
- **Headings**: Geometric and modern typefaces that provide a sleek, functional personality. Scale down appropriately on mobile.
- **Body**: Clean sans-serif aesthetics chosen for high legibility in information-dense views.
- **Mono**: Monospaced fonts used for labels, numerical values, and metadata.

### Responsive Implementation (UnoCSS/Tailwind)
Use fluid typography or breakpoint-specific utility classes to ensure mobile readability without horizontal overflow.

```html
<!-- Responsive Heading structure -->
<h1 class="font-display text-2xl sm:text-3xl md:text-4xl font-bold tracking-tight text-white leading-tight">
  Dashboard Overview
</h1>

<!-- Body text adapting to screen size -->
<p class="font-body text-sm sm:text-base text-gray-400 mt-2 max-w-[65ch]">
  Detailed metrics and system analysis.
</p>

<!-- Tabular data in Mono -->
<span class="font-mono text-xs md:text-sm text-primary tabular-nums">
  1,024.50
</span>
```
