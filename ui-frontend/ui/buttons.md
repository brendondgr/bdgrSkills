# Buttons & Interactive Elements

Interactive controls must be touch-friendly with minimum hit areas of `44x44px` for mobile.

### States & Feedback
- **Hover/Touch**: Themed neon glows or background tinting.
- **Active**: GSAP spring equivalent or CSS scale down (`0.95`).
- **Segmented Controls**: Snappy transitions between active states.

### Implementation Structure (UnoCSS/Tailwind)

```html
<!-- Primary Action Button with Neon Glow -->
<button class="relative w-full sm:w-auto min-h-[44px] px-6 py-2 rounded-full bg-primary text-black font-semibold 
               transition-all duration-300 ease-out hover:shadow-[0_0_20px_rgba(var(--color-primary),0.6)] 
               active:scale-95 flex items-center justify-center gap-2">
  <span>Submit Data</span>
</button>
```

```html
<!-- Mobile-friendly Segmented Control -->
<div class="flex p-1 bg-surface rounded-xl overflow-x-auto select-none touch-pan-x">
  <button class="flex-1 min-w-[80px] min-h-[40px] rounded-lg bg-elevated shadow-sm text-sm font-medium transition-transform active:scale-95">
    View A
  </button>
  <button class="flex-1 min-w-[80px] min-h-[40px] rounded-lg text-gray-400 hover:text-white text-sm font-medium transition-colors">
    View B
  </button>
</div>
```
