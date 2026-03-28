# Modals & Popups

Browser-native dialogs are strictly prohibited. Use custom, application-specific interfaces.

### Design Rules
- **Backdrop**: Blurred, semi-transparent dark overlay.
- **Entrance**: Animate in using GSAP spring curves.
- **Destructive Actions**: Use primary/vibrant red confirmation buttons.

### Structural Example
```html
<!-- Modal Container -->
<div class="fixed inset-0 z-50 flex items-center justify-center bg-black/60 backdrop-blur-sm">
  <!-- Modal Content -->
  <dialog open class="bg-elevated rounded-2xl p-6 border border-white/10 shadow-3xl max-w-md w-full">
    <h2 class="text-xl font-display mb-4">Confirm Deletion</h2>
    <div class="flex justify-end gap-3">
      <button class="text-secondary">Cancel</button>
      <button class="bg-danger text-white px-4 py-2 rounded-md">Delete</button>
    </div>
  </dialog>
</div>
```
