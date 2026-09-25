# Mobile-Native Recipes

Use these recipes as practical fixes for mobile web behavior. Apply them only when the underlying symptom or interaction requires them. Preserve the existing application architecture.

## 1. Fix sticky hover on touch

**Symptom:** A hover style remains after a tap.

Move hover-only visual treatment behind a capability query:

`@media (hover: hover) and (pointer: fine)`

Keep touch feedback in the active/pressed state rather than relying on hover.

---

## 2. Replace tap highlight

**Symptom:** iOS or Android shows a browser tap flash that conflicts with the product's designed feedback.

When the product already provides deliberate press feedback, use:

`-webkit-tap-highlight-color: transparent`

Apply it at the appropriate interactive scope and ensure controls still have clear pressed states.

---

## 3. Use the correct viewport unit

**Symptom:** A full-height mobile app shell overflows or a bottom action sits behind browser chrome.

- Use `dvh` for app shells that should track the visible viewport.
- Use `svh` where a stable minimum viewport is more appropriate, such as a hero where content must never be cut off.
- Avoid assuming `100vh` represents the currently visible mobile viewport.

Test on a real phone because browser chrome behavior is not fully represented by desktop emulation.

---

## 4. Protect content around safe areas

**Symptom:** Fixed headers, bottom bars, or sheets run into the notch, Dynamic Island, or home-indicator area.

Use `viewport-fit=cover` when edge-to-edge rendering is intended, then pad fixed UI with the relevant `env(safe-area-inset-*)` values.

Always include sensible fallbacks when using the values inside calculations.

---

## 5. Prevent input zoom

**Symptom:** Focusing a form field causes the page to zoom on iPhone.

Do not disable browser zoom.

Instead, ensure text inputs, textareas, and selects use a sufficiently large font size, with 16px as a safe baseline for mobile Safari.

Use the project's responsive styling rather than adding JavaScript device detection.

---

## 6. Make tap response immediate

**Symptom:** A control feels laggy even though the underlying action is fast.

Check both:

1. Visual feedback should begin on press, not only after click/release.
2. Avoid unnecessary touch interaction delays.

Use the control's active state for immediate feedback. Use `touch-action: manipulation` only where the interaction semantics support it.

---

## 7. Keep nested scrolling contained

**Symptom:** A sheet, chat list, sidebar, or other scroll area causes the page behind it to move when the inner area reaches an edge.

Prefer CSS `overscroll-behavior` instead of JavaScript scroll interception.

- Use `contain` for nested scroll surfaces that should not chain to their parent.
- Use `none` only when root overscroll behavior genuinely needs to be disabled.

Avoid `touchmove` + `preventDefault()` as a default scroll-control strategy.

---

## 8. Make controls resist accidental text selection

**Symptom:** Long-pressing a control selects its label or opens a browser callout.

Apply `user-select: none` only to controls, tabs, chips, drag handles, and similar UI.

Never disable text selection globally for the body or normal content.

---

## 9. Separate browser scrolling from gestures

**Symptom:** A horizontal carousel scrolls the page vertically or a custom drag conflicts with normal scrolling.

Declare which axes belong to the browser and which belong to the interaction.

Typical patterns:

- horizontal carousel: `touch-action: pan-y`
- vertical gesture surface: preserve horizontal browser panning where appropriate
- custom full gesture ownership: `touch-action: none`, but only on the actual gesture surface

Use native scrolling and scroll snapping when they already solve the interaction.

---

## 10. Make mobile overlays reachable

**Symptom:** A desktop-style dialog or floating action is awkward to operate on a phone.

Consider:

- bottom-oriented sheets for contextual tasks
- full-width or edge-aware primary actions
- reachable fixed actions with safe-area padding
- reduced content density where scanning is difficult

Do not simply shrink the desktop layout. Adapt the interaction model when the device context requires it.

---

## 11. Mobile input ergonomics

**Use when:** A mobile form requires repeated input.

Use semantic HTML and platform hints where they help:

- `type="email"` for email
- `type="tel"` for phone numbers
- `inputmode="numeric"` for numeric codes
- `inputmode="decimal"` for amounts
- `autocapitalize="none"` and `autocorrect="off"` where automatic correction would damage identifiers
- `enterkeyhint` where the next action can be communicated clearly

These hints should reflect the actual field semantics rather than the desired keyboard alone.

---

## 12. Real-device verification

**Use when:** A change affects browser chrome, touch, keyboard, safe areas, or gesture feel.

Verify on physical hardware when possible.

Check at minimum:

- touch feedback
- browser chrome and viewport height
- software keyboard
- safe-area behavior
- scrolling and overscroll
- landscape
- fixed/sticky controls
- installed/PWA mode when relevant

Desktop device emulation is useful for layout, but it is not the final authority for touch behavior.

---

## Technology boundary

These recipes solve mobile-web interaction problems using the platform and the application's existing capabilities.

- Prefer CSS, HTML, browser APIs, and existing components.
- Do not add a mobile framework.
- Do not add a gesture library solely to follow a recipe.
- Do not change routing, state management, data, authentication, or backend architecture for mobile polish.
