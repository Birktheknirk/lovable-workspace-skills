---
name: animation
description: Design and implement purposeful web animation with appropriate timing, easing, properties, and interaction behavior. Use when adding, refactoring, or reviewing transitions, toasts, drawers, popovers, state changes, hover/press feedback, or gesture-driven motion.
---

# Animation

Use motion to improve understanding, feedback, continuity, and responsiveness—not to decorate every interaction.

## Technology boundary

Animation must stay within the project's existing technology stack.

- Prefer the simplest capability already available in the project.
- Prefer CSS for simple, predictable UI transitions.
- Use an already-installed advanced motion capability only when the interaction genuinely requires it.
- Do not add, replace, or recommend an animation library solely to follow this skill.
- Do not replace existing components or architectural patterns to implement animation.
- If a motion pattern appears to require a technology change, adapt the motion to the existing project instead.

## Build sequence

Follow this order when adding or redesigning motion.

### 1. Decide whether it should animate

Do not animate automatically.

Consider how often the interaction occurs and whether motion adds meaningful feedback or orientation.

- High-frequency or keyboard-driven actions: usually no animation.
- Frequent interactions: keep feedback extremely subtle or instant.
- Occasional surfaces such as dialogs, drawers, and toasts: normal UI motion can be useful.
- Rare or first-time moments: a small amount of delight can be appropriate when it supports the product.

If the only reason is "it looks cool", do not add motion to a frequently used interaction.

### 2. Name the purpose

Every animation should serve at least one clear purpose:

- feedback
- spatial continuity
- state indication
- preventing an abrupt change
- direct manipulation
- explanation
- deliberate delight

If no purpose can be stated, prefer no animation.

### 3. Choose the simplest implementation

Use this implementation hierarchy:

1. Existing project CSS/transitions.
2. Existing project primitives or component capabilities.
3. Existing advanced motion capability when dynamic or gesture-driven behavior requires it.
4. A new dependency only when explicitly approved or when the project genuinely has no suitable existing capability.

Do not change the technology stack to obtain a nicer animation.

## Properties

Prefer compositor-friendly properties such as:

- `transform`
- `opacity`

Use other properties only when they are appropriate to the specific interaction and cannot be replaced cleanly.

Avoid animating layout-heavy properties unnecessarily, especially `width`, `height`, `margin`, `padding`, `top`, and `left`.

Avoid `scale(0)` for entry states. A small scale combined with opacity generally feels more natural.

For anchored surfaces such as popovers and tooltips, use an origin that reflects the trigger when the existing component system supports it. Centered dialogs should remain centered.

## Timing

Use these as starting ranges:

| Interaction | Starting range |
| --- | --- |
| Press feedback | 100-160ms |
| Tooltips / small popovers | 125-200ms |
| Menus / selects | 150-250ms |
| Modals / drawers | 200-300ms for ordinary UI |

Longer motion is acceptable only when the extra duration contributes to orientation, direct manipulation, or explanation.

The user's ability to continue the task should take priority over the animation finishing.

## Easing

Use easing that matches the motion:

| Situation | Starting choice |
| --- | --- |
| Entering / exiting | ease-out |
| Movement / morphing | ease-in-out |
| Hover / color change | ease |
| Constant motion | linear |

Avoid slow-starting ease-in curves for ordinary UI feedback.

When the project already has motion tokens or curves, reuse them instead of creating a parallel system.

## Interruptibility

Animations should behave well when the user changes their mind.

- Prefer transitions for rapidly changing UI states when they can retarget naturally.
- Do not lock interaction while an animation is running.
- For gesture-driven interactions, the visual state should track the user's input directly.
- When a drag is released, the settling motion should begin from the current presentation state rather than a stale logical target.
- Preserve velocity when the existing project motion capability supports it.

Do not fake gesture-driven behavior with a fixed animation that finishes before the user can interact again.

## Spatial continuity

Movement should explain relationships.

- An element should generally enter and exit along related paths.
- Anchored surfaces should feel connected to their trigger.
- A dialog is a centered surface, not an anchored popover.
- Reversible interactions should feel reversible rather than snapping between unrelated positions.

## Reduced motion and pointer capability

Accessibility is part of the initial implementation.

For reduced motion:

- remove or substantially reduce non-essential positional movement
- preserve useful opacity/color feedback where appropriate
- remove elastic, parallax, and large movement effects

For hover:

- use hover-specific motion only where the device supports genuine hover
- do not rely on hover for touch interaction

## Performance

Prioritize actual responsiveness over decorative motion.

- Avoid unnecessary per-frame work.
- Prefer `transform` and `opacity` for moving elements.
- Do not use animation to disguise slow data fetching or expensive rendering.
- Avoid updating broad parent styles when only one animated element needs to move.
- Keep high-frequency animations visually simple.

## Recipes

For common implementation patterns, consult [RECIPES.md](RECIPES.md). Use the relevant recipe as a starting point and adapt it to the existing project rather than applying it literally.

## Final check

Before finishing, verify:

1. The animation has a clear purpose.
2. The chosen implementation is the simplest suitable existing capability.
3. The timing does not delay the user's task.
4. The interaction can respond to a changed state.
5. Reduced-motion and hover behavior are covered where relevant.
6. No new dependency or competing technology was introduced.
