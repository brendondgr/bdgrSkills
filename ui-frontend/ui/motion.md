# Motion & Animations

Powered by **GSAP** and CSS. Animations should feel intentional, fluid, and tactical.

### Core Behaviors
- **Micro-interactions**: Use GSAP `CustomEase` or `elastic` for a snappy, springy feel.
- **Load Sequences**: Prefer staggered reveals (`animation-delay`) over scattered motion.
- **Visibility**: Fade-in to `100%` opacity. If an element starts on-screen, it must be instantly visible.

### Structural Example
```javascript
// GSAP Stagger Reveal
gsap.from(".card", {
  y: 30,
  opacity: 0,
  stagger: 0.1,
  ease: "power3.out"
});
```

```css
/* CSS Hover Lift */
.hover-card {
  transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}
.hover-card:hover {
  transform: translateY(-4px) scale(1.02);
}
```
