# Motion & Animations

GSAP is the standard for complex programmatic animations. CSS is used for simple micro-interactions.

### Rules
- **Micro-animations**: Use GSAP `CustomEase` or CSS `cubic-bezier` for spring/elastic, snappy feel.
- **Visibility**: Elements entering the screen should fade/slide in to `opacity: 1`. Elements starting on-screen must be `100%` visible immediately.
- **Hover Lift**: Cards feature a hover lift effect and slight scale-up. On mobile, map these to touch active states.

### GSAP Implementation (React Example)

```jsx
// React + GSAP Stagger Reveal
import { useLayoutEffect, useRef } from 'react';
import gsap from 'gsap';

export function AnimatedList({ items }) {
  const container = useRef();
  
  useLayoutEffect(() => {
    gsap.from(container.current.children, {
      y: 20,
      opacity: 0,
      stagger: 0.05,
      ease: "power3.out",
      duration: 0.6
    });
  }, []);

  return <ul ref={container} className="space-y-2">{/* items */}</ul>;
}
```

### CSS Implementation (UnoCSS/Tailwind)

```html
<!-- Interactive Card with Hover Lift -->
<div class="transform transition-all duration-300 ease-out hover:-translate-y-1 hover:scale-[1.02] active:scale-[0.98] active:translate-y-0 shadow-lg hover:shadow-xl">
  Card Content
</div>
```
