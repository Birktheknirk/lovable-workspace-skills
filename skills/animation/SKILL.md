---
name: animation
description: Design and implement purposeful web animation with appropriate timing, easing, properties, and interaction behavior. Use when adding, refactoring, or reviewing transitions, toasts, drawers, popovers, state changes, hover/press feedback, or gesture-driven motion.
---

# Animation

Use motion to improve understanding and responsiveness, not to decorate every interaction.

## Technology boundary

Animation guidance must work within the project's existing stack.

- Prefer CSS transitions for simple UI state changes when they are sufficient.
- Use an existing animation capability already installed in the project for advanced motion.
- Do not add an animation library solely because a skill mentions one.
- Do not replace existing UI components or architectural patterns to implement motion.

## Decide whether to animate

Before adding motion, identify the reason. Good reasons include:

- immediate interaction feedback
- showing where something came from or went to
- communicating a state transition
- preventing an abrupt visual replacement
- supporting direct manipulation or gestures

Avoid animation for high-frequency actions when it adds noticeable delay or visual noise.

## Timing defaults

Keep ordinary UI motion short and responsive.

Use roughly:

- press feedback: 100-160ms
- tooltips and small popovers: 125-200ms
- menus and selects: 150-250ms
- modals and drawers: 200-500ms when the larger movement genuinely helps orientation

Treat these as starting points, not rigid requirements.

## Easing

Default interactive entrances to an ease-out feel: fast response first, then settle.

Use ease-in-out for movement that travels across the screen and needs a sense of acceleration and deceleration.

Use linear easing for truly constant motion such as progress indicators.

Avoid slow-starting ease-in curves for ordinary UI feedback.

## Properties

Prefer animating transform and opacity when possible.

Avoid animating layout-heavy properties unnecessarily.

For popovers and anchored surfaces, make the transform origin follow the source when the component system supports it. Centered dialogs should remain centered.

## Interruptibility

For ordinary state changes, prefer transitions that can respond gracefully when the state changes again.

For gesture-driven interactions, the visual state should track the user's input directly and be capable of reversing without a visible jump. Use the project's existing advanced motion primitive when that behavior cannot be achieved cleanly with CSS.

## Enter/exit

Avoid making elements appear from absolute zero scale. A subtle scale combined with opacity generally feels more natural.

Keep entering and exiting spatially consistent: an element should leave through a path that relates to how it entered.

## Reduced motion

Respect `prefers-reduced-motion`. Remove or significantly reduce non-essential movement when the user has requested reduced motion.

## Perceived performance

Do not use animation to hide genuine slowness. Make transitions feel immediate, but keep data loading, rendering, and interaction latency as the real priority.
