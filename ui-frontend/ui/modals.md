# Modals & Popups

Browser-native dialogs are forbidden. Use custom, responsive glassmorphism modals.

### Behavior
- **Backdrop**: Blurred, semi-transparent dark overlay.
- **Mobile handling**: Modals should act as bottom sheets on very small screens, and centered popups on desktop.
- **Entrance**: Animate in using GSAP spring curves.

### Confirmations & Prompts
Strictly prohibit the use of native browser popups: `window.alert()`, `window.confirm()`, or `window.prompt()`. 
Whenever a user action requires confirmation (e.g., deleting a file, submitting forms, or saving changes), a custom modal or toast notification must be triggered instead. 

### Implementation Guidelines
- **Structure**: Utilize headless UI components or native `<dialog>` elements styled with Tailwind/UnoCSS.
- **Backdrop**: Blurred, semi-transparent dark overlay (e.g., `bg-black/60 backdrop-blur-sm`).
- **Mobile handling**: Modals should act as bottom sheets on very small screens (with a visual drag-handle indicator), and centered popups on desktop.
- **Entrance**: Animate in using GSAP spring curves or quick CSS transitions.
- **Focus Trap**: Ensure keyboard focus is trapped within the active modal and closing the modal returns focus to the trigger element.
- **Actions**: Provide clear, touch-friendly primary and secondary action buttons with minimum `44x44px` hit areas.
