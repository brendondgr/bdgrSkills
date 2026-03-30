# Dropdowns & Selects

Default browser `<select>` dropdowns frequently introduce harsh white backgrounds and black text that break the immersive dark-mode aesthetic. All dropdowns in the application must use custom UI implementations.

### Aesthetics & Theme Alignment
- **Background**: Menus use the `Elevated` (`#1e1e1e`) or `Surface` (`#141414`) background colored to stand out against the `Base` background (`#0a0a0a`).
- **Text & Contrast**: High-contrast white or light gray text. The stark white-to-black color flip from default operating system dropdowns must be avoided.
- **Hover/Focus**: Interactive items should feature a subtle neon background tint (e.g., 5-10% opacity cyber cyan or matrix mint) rather than solid white.
- **Active/Selected**: Selected items are indicated by a vibrant neon text accent or a subtle left-border indent.

### Implementation Guidelines
- **Structure**: Utilize headless UI components (e.g., Radix UI, Headless UI) styled with Tailwind/UnoCSS to ensure keyboard accessibility and screen reader support while keeping complete DOM customization.
- **Animation**: Implement quick CSS scale-in and fade-in transitions (`duration-200 ease-out`) or GSAP staggered list animations when the menu is opened. Avoid clunky sudden appearances.
- **Mobile Adjustments**: On mobile viewports, complex dropdowns should adapt into touch-pan-friendly bottom sheets to ensure minimum `44x44px` hit areas.