# Colors & Themes

Dark-themed, high-contrast palette avoiding generic gradients. Focus on dominant colors with sharp accents.

### Color Tokens
- **Background**: Deep Matte Black `#0a0a0a`
- **Surface**: Dark Gray `#141414` (Cards, panels)
- **Elevated**: Lighter Gray `#1e1e1e` (Modals, popups)

### Brand Roles
- **Primary**: Neon/vibrant for critical actions.
- **Secondary**: Muted cool tones for navigation.
- **Danger**: High-visibility alert reds.

### Implementation Example
```css
/* CSS Variables defined in variables.css */
.theme-container {
  background: var(--bg-matte);
  border: 1px solid var(--border-vibrant);
}
```
