# Modals & Popups

Browser-native dialogs are forbidden. Use custom, responsive glassmorphism modals.

### Behavior
- **Backdrop**: Blurred, semi-transparent dark overlay.
- **Mobile handling**: Modals should act as bottom sheets on very small screens, and centered popups on desktop.
- **Entrance**: Animate in using GSAP spring curves.

### Implementation Structure (React / Tailwind)

```jsx
// Modal Layout Wrapper
<div className="fixed inset-0 z-50 flex items-end sm:items-center justify-center p-0 sm:p-4">
  {/* Backdrop */}
  <div className="absolute inset-0 bg-black/60 backdrop-blur-sm" onClick={onClose} />
  
  {/* Dialog Box (Bottom sheet on mobile, centered rounded rect on desktop) */}
  <dialog 
    open 
    className="relative w-full sm:w-auto sm:max-w-lg bg-elevated rounded-t-2xl sm:rounded-2xl border-t sm:border border-white/10 shadow-2xl p-6 m-0"
  >
    <div className="w-12 h-1 bg-white/20 rounded-full mx-auto mb-6 sm:hidden" /> {/* Mobile Drag Handle indicator */}
    <h2 className="text-xl font-display mb-4 text-white">Perform Action?</h2>
    <div className="flex flex-col-reverse sm:flex-row justify-end gap-3 mt-8">
      <button className="w-full sm:w-auto px-4 py-3 sm:py-2 rounded-lg bg-surface text-gray-300 min-h-[44px]">Cancel</button>
      <button className="w-full sm:w-auto px-4 py-3 sm:py-2 rounded-lg bg-danger text-white font-medium min-h-[44px]">Confirm</button>
    </div>
  </dialog>
</div>
```
