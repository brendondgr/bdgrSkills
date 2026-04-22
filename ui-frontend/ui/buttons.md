# Buttons & Interactive Elements

Interactive controls must enforce a mobile-first design system with generous minimum touch/hit areas of `44x44px`. All interactive components must be rigorously keyboard navigable.

### Accessibility & Interaction States
- **Focus Indicators**: Every interactive button must display a high-contrast focus ring (e.g., `focus-visible:ring-2 focus-visible:ring-primary focus-visible:outline-none`) when navigated via keyboard. Ensure focused elements are not clipped or hidden.
- **Labels & Context**: Icon-only buttons must provide an `aria-label` or visually hidden screen reader text. Links posing as buttons should be `<a>` elements with proper readable text instead of relying on "Click Here" or "Read More".
- **Hover/Touch**: Themed neon glows or background tinting. Active states provide immediate feedback.
- **Contrast**: Button text foreground must meet **4.5:1** contrast with its background, while the physical button borders or background must maintain **3:1** against the body text.
- **Segmented Controls**: Snappy transitions between active states without losing keyboard arrow-key support.

### Implementation Structure (UnoCSS/Tailwind)

```html
<!-- Accessibility-first Primary Action Button -->
<button class="relative w-full sm:w-auto min-h-[44px] px-6 py-2 rounded-full bg-primary text-black font-semibold 
               focus-visible:ring-2 focus-visible:ring-white focus-visible:ring-offset-2 focus-visible:ring-offset-black
               transition-all duration-300 ease-out hover:shadow-[0_0_20px_rgba(var(--color-primary),0.6)] 
               active:scale-95 flex items-center justify-center gap-2"
        aria-label="Submit Form Data">
  <span>Submit Data</span>
</button>
```

```html
<!-- Mobile-friendly Segmented Control with Touch Panning -->
<div role="group" aria-label="View Selection" class="flex p-1 bg-surface rounded-xl overflow-x-auto select-none touch-pan-x">
  <button aria-pressed="true" class="flex-1 min-w-[80px] min-h-[44px] rounded-lg bg-elevated shadow-sm text-sm font-medium transition-transform active:scale-95 focus-visible:ring-2 focus-visible:ring-primary">
    View A
  </button>
  <button aria-pressed="false" class="flex-1 min-w-[80px] min-h-[44px] rounded-lg text-gray-300 hover:text-white text-sm font-medium transition-colors focus-visible:ring-2 focus-visible:ring-primary">
    View B
  </button>
</div>
```
