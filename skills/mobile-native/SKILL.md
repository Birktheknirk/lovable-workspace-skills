---
name: mobile-native
description: Make a responsive web app feel native on phones and touch devices. Use when building or reviewing mobile layouts, touch interactions, bottom sheets, full-screen surfaces, carousels, inputs, fixed navigation, or any UI that feels correct on desktop but awkward on a real phone.
---

# Mobile-Native Web

Make the web interface behave like a mobile product rather than a desktop layout squeezed into a phone.

## Technology boundary

Use the platform and the project's existing components before adding JavaScript or dependencies.

- Do not add a mobile framework.
- Do not add a gesture library solely to solve mobile polish.
- Do not change routing, state management, data, authentication, or backend architecture for mobile behavior.
- Prefer capability-based CSS and existing project primitives.
- If a mobile pattern appears to require a technology change, adapt the pattern to the existing project instead.

## Hard rules

- Treat touch, mouse, keyboard, and trackpad as potentially coexisting inputs.
- Prefer input capabilities such as hover and pointer queries over user-agent or device-name detection.
- Never disable browser zoom for accessibility reasons.
- Give interactive controls clear press feedback.
- Test touch behavior on real hardware before calling touch-specific work complete when possible.

## Diagnose the symptom first

When reviewing or fixing mobile behavior, identify the actual symptom before changing code.

| Symptom | Typical direction |
| --- | --- |
| Hover state sticks after tap | Gate hover styles by hover/pointer capability |
| Tap flash conflicts with designed feedback | Replace browser highlight with deliberate control feedback |
| Full-height layout overflows mobile chrome | Use the appropriate modern viewport unit |
| Input causes unwanted zoom | Use an adequate input font size; never disable zoom |
| Tap feels delayed | Provide press feedback early and remove unnecessary interaction delay |
| Nested scroll moves the page behind it | Use `overscroll-behavior` |
| Content collides with notch/home indicator | Use safe-area insets with edge-to-edge viewport handling |
| Long-press selects control text | Disable selection only on controls |
| Carousel competes with page scrolling | Declare the intended touch axes |
| Layout is correct in emulation but wrong on phone | Verify on real hardware |

For concrete fixes, consult [RECIPES.md](RECIPES.md).

## Hover and touch

Do not rely on hover for touch behavior.

- Put hover-only visual effects behind capability queries such as `(hover: hover) and (pointer: fine)`.
- Provide useful active/pressed feedback independently.
- Do not infer touch capability from screen width or user-agent strings.

## Viewport and safe areas

Choose viewport behavior according to the surface:

- Use `dvh` when an app shell should follow the currently visible viewport.
- Use `svh` when a stable minimum viewport is more important.
- Do not assume `100vh` equals the visible mobile viewport.

For fixed elements near screen edges, account for safe-area insets where the platform exposes them.

## Inputs and keyboard

Mobile inputs should be easy to use and should communicate their intended input type to the platform.

- Avoid undersized input text that causes unwanted mobile zoom.
- Use semantic input types and input modes.
- Use keyboard hints only when they match the field's actual purpose.
- Test forms with the software keyboard open because it changes the usable viewport.

## Scrolling and touch ownership

Prefer browser-native scrolling and CSS behavior over JavaScript interception.

- Use `overscroll-behavior` to control scroll chaining.
- Use `touch-action` to describe which axes the browser may handle.
- Use native scroll snapping when it solves a carousel or paging problem.
- Avoid global `touchmove` prevention as a default scrolling strategy.

## Mobile interaction posture

Adapt the interaction model when needed instead of shrinking desktop UI.

Prefer:
- reachable primary actions
- edge-aware or bottom-oriented contextual surfaces when appropriate
- comfortable touch spacing
- concise information hierarchy
- controls that remain visible and usable around browser/device UI

Avoid:
- hover-dependent actions
- precision-only interactions
- fixed elements that cover content
- desktop tables with no mobile strategy
- unnecessarily large controls created only to satisfy touch target concerns

## Accessibility

Mobile polish must not trade away accessibility.

- Never disable zoom.
- Keep normal content selectable.
- Preserve keyboard focus behavior for external keyboards and hybrid devices.
- Ensure touch feedback does not replace an accessible state.
- Provide reduced-motion behavior for substantial movement when the interaction also uses animation.

## Verification

Code inspection can confirm declarations and interaction logic, but some mobile behaviors require a real device.

When possible, test:
- touch and press feedback
- browser chrome and viewport height
- software keyboard
- safe areas
- nested scrolling and overscroll
- landscape
- fixed/sticky controls
- installed/PWA mode when relevant

Do not claim a phone-specific behavior is verified if it was only tested in desktop device emulation.