Here is a comprehensive ADA compliance checklist based on the **WCAG 2.2 AA standard** — the current benchmark for ADA website compliance. You can hand this directly to an AI to audit each page.

***

## 🖼️ Images & Non-Text Content

- [ ] Every meaningful image has descriptive `alt` text
- [ ] Decorative images use empty alt text (`alt=""`) or are set as CSS backgrounds 
- [ ] Complex images (charts, graphs, maps) have extended descriptions in text or on a linked page 
- [ ] Images of text are avoided unless essential (e.g., logos)
- [ ] Linked images have descriptive alt text explaining the link destination 

***

## 🎬 Audio & Video

- [ ] All prerecorded video has synchronized closed captions 
- [ ] All prerecorded audio-only content (podcasts, MP3s) has a text transcript 
- [ ] Prerecorded videos have audio descriptions for important visual content not in the audio track 
- [ ] Live audio or video presentations have synchronized captions 
- [ ] Audio that auto-plays for more than 3 seconds has a visible pause/stop/mute control 

***

## 🏗️ Structure & Semantics

- [ ] Pages use proper semantic HTML heading hierarchy (`<h1>` through `<h6>`)
- [ ] Headings and labels are clear and descriptive — no vague labels like "Click Here"
- [ ] Lists use proper `<ul>`, `<ol>`, or `<dl>` markup 
- [ ] Data tables use `<th>` headers with `scope` attributes, and have captions where needed 
- [ ] The page `lang` attribute is set correctly (e.g., `<html lang="en">`) 
- [ ] If any content is in a different language than the page, that section uses its own `lang` attribute 
- [ ] Content reads in a logical order when CSS is stripped 

***

## 🎨 Color & Visual Design

- [ ] Text has a minimum contrast ratio of **4.5:1** against its background 
- [ ] Large text (18pt or 14pt bold) has a minimum contrast ratio of **3:1** 
- [ ] Non-text UI elements (buttons, icons, form inputs) have a minimum contrast ratio of **3:1**
- [ ] Color is not the only way information is conveyed (e.g., error states use icons or text too) 
- [ ] Page is readable and functional when zoomed to **200%** without content loss
- [ ] Page content reflows at **320px width** (400% zoom on a 1280px screen) without horizontal scrolling 
- [ ] Text spacing (line height, letter/word spacing) can be adjusted by users without breaking layout 

***

## ⌨️ Keyboard & Navigation

- [ ] **All functionality is operable using only a keyboard** (no mouse required)
- [ ] No keyboard traps — users can navigate to and away from all elements 
- [ ] A visible focus indicator is shown on every interactive element when focused 
- [ ] Focused elements are **not hidden or obscured** by sticky headers, overlays, etc.
- [ ] A "Skip to Main Content" link is provided to bypass repeated navigation 
- [ ] Tab/focus order is logical and follows the visual reading flow 
- [ ] If keyboard shortcuts use single printable characters, users can disable or remap them 
- [ ] Interactive target sizes are at least **24×24 CSS pixels**

***

## 📝 Forms

- [ ] Every form input has a visible, programmatically associated `<label>` 
- [ ] Required fields are clearly identified (not just by color)
- [ ] Error messages are descriptive, specific, and announced to screen readers
- [ ] Error suggestions are provided when input validation fails 
- [ ] Input fields that collect personal data (name, email, address, etc.) use proper `autocomplete` attributes 
- [ ] Forms that involve legal, financial, or test submissions allow review, confirmation, or reversal 
- [ ] Authentication does not require solving a puzzle or memorizing data without an accessible alternative 
- [ ] Information entered earlier in a session is auto-populated when re-entry is required

***

## 🔗 Links & Buttons

- [ ] Link text is descriptive on its own — avoid "click here," "read more," or "learn more"
- [ ] Links with identical text do not point to different destinations 
- [ ] Buttons have descriptive, accessible names/labels 
- [ ] Links that open new tabs or download files indicate this in the link text or via an icon with alt text

***

## 📄 Page-Level Requirements

- [ ] Every page has a unique, descriptive `<title>` tag
- [ ] Multiple ways to find pages exist: search, sitemap, navigation menu, breadcrumbs, etc.
- [ ] Navigation menus appear in a **consistent location and order** across all pages 
- [ ] UI components with the same function are **consistently labeled** across pages 
- [ ] Help options (contact info, support links) are consistently placed across pages 
- [ ] No content flashes more than **3 times per second** (seizure risk) 

***

## 📱 Motion & Dynamic Content

- [ ] Auto-moving, blinking, or scrolling content (carousels, animations) can be paused, stopped, or hidden 
- [ ] Content orientation is **not locked** to portrait or landscape unless absolutely necessary
- [ ] Touch/pointer gestures have single-tap alternatives (no swipe-only required actions)
- [ ] Device-motion-triggered functions (shake, tilt) have button-based alternatives and can be disabled 
- [ ] Hover/focus tooltips or popups can be dismissed without moving focus (usually via Esc key) and don't disappear when hovering over them 
- [ ] Draggable interactions have a single-click/tap alternative

***

## ⚙️ Code & Compatibility

- [ ] HTML is well-formed and free of significant parsing errors 
- [ ] All UI components have programmatically determinable name, role, and state (use ARIA where native HTML is insufficient) 
- [ ] Status messages (e.g., "Item added to cart") are announced to screen readers via ARIA live regions without moving focus 
- [ ] No context changes happen automatically on focus — only on deliberate user input 
- [ ] Pages do not auto-submit or cause layout changes without warning on user input 
- [ ] iFrames and embedded content have descriptive `title` attributes 

***

> **Tip:** The legally required standard for most websites is **WCAG 2.1 AA** (minimum), with **WCAG 2.2 AA** now strongly recommended as the current best practice. Addressing the items above covers all Level A and AA criteria across both versions.