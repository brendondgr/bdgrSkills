Here is a comprehensive, well-organized checklist covering everything required to make a website completely mobile-friendly.

***

## 📱 Mobile-Friendly Website Checklist

### 1. Responsive Layout & Viewport

- **Add the viewport meta tag** — every page must include `<meta name="viewport" content="width=device-width, initial-scale=1">` in `<head>`
- **Design mobile-first** — start at 375px width, then scale up using `min-width` media queries
- **Use flexible CSS Grid/Flexbox** — no fixed-pixel layouts; use `%`, `fr`, `clamp()`, and `auto-fill` for fluid grids
- **Test at key breakpoints:** 375px (iPhone SE), 390px (iPhone 14), 768px (iPad), 1024px+
- **Single-column layout on small screens** — collapse multi-column grids into stacked single columns on mobile
- **Prevent horizontal scrolling** — set `max-width: 100%` on images, videos, and embeds; use `overflow-x: hidden` on body if needed

***

### 2. Typography & Readability

- **Body text minimum 16px** — prevents iOS from auto-zooming on input focus and ensures comfortable reading
- **Line height 1.5–1.75em** for body copy to improve legibility on small screens
- **Use fluid type scaling** with `clamp()` so text scales smoothly without breaking layouts
- **High contrast text** — minimum 4.5:1 contrast ratio for body text (WCAG AA)
- **Limit line length** — `max-width: 65–75ch` on paragraphs; don't let text stretch edge-to-edge on wide phones
- **Never use text smaller than 12px** — this is the absolute minimum floor for labels and metadata

***

### 3. Touch & Navigation

- **Touch targets minimum 44×44px** — buttons, links, nav items, and form controls must be large enough to tap comfortably
- **Space tap targets apart** — add padding between links; avoid stacked clickable elements too close together
- **Visible `:active` states** — every tappable element must give visual feedback when tapped
- **No hover-only UI** — replace hover-dependent tooltips/menus with tap/toggle patterns; use `@media (hover: none)` to detect touch
- **Mobile navigation pattern** — 5 or fewer items → bottom tab bar; more items → hamburger with grouped sections
- **Bottom-anchored primary CTAs** — place critical actions within thumb reach, consider sticky bottom bars
- **Avoid fixed elements blocking content** — don't stack sticky header + sticky footer + cookie banner simultaneously on mobile

***

### 4. Images & Media

- **Use `srcset` and `sizes` attributes** — serve appropriately sized images for each screen resolution
- **Modern formats (WebP / AVIF)** — 25–50% smaller than JPEG with equivalent quality
- **Lazy load below-the-fold images** — add `loading="lazy"` and `decoding="async"` to all `<img>` tags
- **Always set `width` and `height` attributes** — prevents Cumulative Layout Shift (CLS) as images load
- **Compress all images** — use tools like Squoosh or ImageOptim before deploying
- **Video: use `<video>` with `playsinline`** — prevents iOS from forcing full-screen playback

***

### 5. Performance & Core Web Vitals

- **LCP (Largest Contentful Paint) < 2.5s** — the largest visible element must load fast
- **INP (Interaction to Next Paint) < 200ms** — interactions must feel snappy
- **CLS (Cumulative Layout Shift) < 0.1** — content must not jump around while loading
- **Minify and bundle CSS/JS** — remove unused code, defer non-critical JavaScript
- **Use a CDN** — serve assets from edge locations closer to users
- **Implement browser caching** — set appropriate `Cache-Control` headers for static assets
- **Total page weight under 1.5MB** on initial load (aim for under 800KB for informational sites)
- **Skeleton loaders** — show shimmering placeholder layouts while content loads instead of blank screens

***

### 6. Forms & Inputs

- **Use semantic input types** — `type="email"`, `type="tel"`, `type="number"` trigger the correct mobile keyboard
- **Enable autocomplete** — add `autocomplete="email"`, `autocomplete="name"`, etc. to reduce typing friction
- **Large input fields** — inputs should be at least 44px tall; avoid tiny checkboxes and radio buttons
- **Minimize form fields** — use progressive disclosure; break long forms into multi-step flows
- **Inline validation** — show errors next to the relevant field, not just at form submission

***

### 7. SEO & Google Mobile-First Indexing

- **Content parity** — your mobile version must contain the same meaningful content as desktop; Google indexes the mobile version first
- **Same meta robots tags** — don't apply `noindex` or `nofollow` only to mobile pages
- **Consistent structured data** — schema markup must appear on both mobile and desktop versions
- **Canonical tags** — ensure canonical URLs match between mobile and desktop
- **Don't block CSS, JS, or images from Googlebot** — Google's mobile crawler must be able to fully render your pages

***

### 8. Accessibility on Mobile

- **Support screen readers** — test with VoiceOver (iOS) and TalkBack (Android)
- **Semantic HTML** — use `<header>`, `<nav>`, `<main>`, `<article>`, `<footer>` for logical structure
- **Alt text on all images** — descriptive `alt` for content images, `alt=""` for decorative ones
- **Don't rely on color alone** — pair color cues with icons, text labels, or patterns for errors/success states
- **Keyboard/switch navigation** — all interactive elements must work via sequential navigation
- **Respect `prefers-reduced-motion`** — disable animations for users who have set this preference