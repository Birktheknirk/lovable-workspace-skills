---
name: mobile-native
description: Make a responsive web app feel native on phones and touch devices. Use when building or reviewing mobile layouts, touch interactions, bottom sheets, full-screen surfaces, carousels, inputs, fixed navigation, or any UI that feels correct on desktop but awkward on a real phone.
---

# Mobile-Native Web

Make the web interface behave like a mobile product rather than a desktop layout squeezed into a phone.

## Technology boundary

Apply platform-level CSS, HTML, and existing component patterns before adding JavaScript or dependencies.

- Do not add a mobile framework.
- Do not add a gesture library unless the project already uses one and it is genuinely required.
- Do not change routing, state management, or backend architecture for mobile polish.
- Prefer capability-based CSS and existing project primitives.

## Hard rules

- Test touch behavior on real hardware before declaring it complete when possible.
- Prefer media queries based on input capabilities over user-agent or device-name detection.
- Treat touch, mouse, keyboard, and trackpad as potentially coexisting inputs.
- Never disable browser zoom for accessibility reasons.
- Give interactive controls clear press feedback.

## Common mobile issues

### Hover
Do not rely on hover for touch behavior. Gate hover-only visual effects behind pointer/hover capability queries when necessary.

### Tap feedback
Avoid default tap flashes when they conflict with a deliberate interaction design, and replace the removed feedback with a clear active/press state.

### Viewport height
Prefer modern viewport units such as `dvh` for app shells where browser chrome can change the visible height.

### Safe areas
Account for device safe areas when content is fixed near the top or bottom edges.

### Inputs
Avoid mobile text zoom caused by undersized inputs. Use appropriate input types and keyboard hints where they improve the experience.

### Scrolling
Use `overscroll-behavior` and appropriate touch-action values instead of JavaScript scroll interception whenever possible.

### Touch targets
Make controls easy to hit without making the visual UI unnecessarily oversized. Keep primary actions comfortable and predictable.

## Mobile-specific UI posture

Prefer:

- clear full-width or edge-aware actions
- sheets and drawers for contextual tasks when they fit the interaction
- sticky actions that remain reachable
- generous touch spacing
- concise information hierarchy

Avoid:

- desktop tables with no mobile strategy
- hover-dependent controls
- tiny icon-only targets without accessible labels
- fixed elements that cover content
- interactions that require precision tapping
