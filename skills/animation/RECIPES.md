# Animation Recipes

Use these recipes as starting patterns. Adapt them to the existing component system and interaction model. Do not add dependencies to use a recipe.

## 1. Press feedback

**Use when:** A pressable control needs immediate tactile feedback.

Use a short transition on `transform`, then apply a subtle `scale(0.97)` on the active/pressed state. Keep the effect subtle and preserve keyboard focus styling.

## 2. Small popover or tooltip

**Use when:** A contextual surface appears from a trigger.

- Enter quickly with an ease-out curve.
- Start slightly smaller and transparent rather than at `scale(0)`.
- Anchor the transform origin to the trigger when the component exposes that capability.
- Exit cleanly and avoid leaving the user waiting.

A typical starting point is 125-200ms.

## 3. Dialog

**Use when:** A modal interrupts the current task and needs spatial acknowledgment.

- Keep the dialog centered unless the product uses a deliberate alternative.
- Use restrained opacity/scale or opacity/translate motion.
- Keep the transition short and reversible.
- Pair with an appropriate backdrop rather than relying on motion alone.

A typical starting point is 200-300ms; use longer only when the larger movement genuinely improves orientation.

## 4. Drawer or sheet

**Use when:** A surface enters from an edge and remains spatially connected to that edge.

- Enter quickly.
- Use the direction of travel to explain where the surface came from.
- Prefer `transform` over layout changes for movement.
- Keep dismissal on the same spatial path.
- For direct drag interactions, let the surface follow the pointer and preserve release velocity when the existing project capability supports it.

For a non-gesture entry, `cubic-bezier(0.32, 0.72, 0, 1)` is a useful starting curve.

## 5. Rapidly changing state

**Use when:** A control can change state repeatedly in quick succession.

Prefer CSS transitions over fixed keyframes when the transition needs to retarget from the current value.

Examples: toggles, toast stacks, frequently updated status indicators, repeated expand/collapse actions.

Do not make the user wait for a previous animation to finish before the next interaction takes effect.

## 6. List entrance

**Use when:** A group of related items enters together and a small amount of sequencing improves orientation.

- Keep the movement subtle.
- Use a short stagger, typically 30-80ms.
- Never block interaction while the stagger plays.
- Do not stagger large datasets or high-frequency updates.

For ordinary UI, opacity plus a small translate is usually enough.

## 7. State crossfade

**Use when:** Two visual states replace each other and the swap otherwise feels abrupt.

- Crossfade the relevant content rather than animating unrelated layout.
- Keep the duration short.
- When two states visually overlap awkwardly, a very subtle temporary blur can help bridge the transition.
- Remove the blur promptly; it should never become part of the resting UI.

## 8. Gesture-to-settle

**Use when:** The user drags or flicks a surface and the UI needs to settle afterward.

The interaction should be: direct while dragging, continuous through release, and settled by the simplest existing motion primitive that preserves the current state naturally.

For momentum-driven interactions, carry release velocity into the settling motion when the project already supports it.

Avoid snapping only from a stale logical target, hard boundary stops, or restarting from an outdated value after interruption.

## 9. Rubber-band boundary

**Use when:** A draggable surface reaches a natural boundary.

Allow a small amount of additional movement with increasing resistance rather than an abrupt stop.

Use this for sheets, carousels, and overscroll-like interactions. Keep the effect subtle and never let it compromise the boundary itself.

## 10. Hold-to-confirm

**Use when:** An action is deliberately committed by holding rather than tapping.

- Show progress continuously while the pointer/touch is held.
- Use linear timing for the deliberate hold period.
- On release or completion, respond quickly.
- Make cancellation obvious.

For a destructive hold, around 2 seconds is a reasonable starting point; release should cancel or complete immediately rather than waiting for another animation.

## 11. Reduced-motion variant

Every non-essential movement should have a reduced-motion path.

Keep feedback and state communication where possible, but remove large positional movement, parallax, elastic motion, and unnecessary scaling when `prefers-reduced-motion` is enabled.

## 12. Hover feedback

Only use hover-specific motion when the device supports real hover. A suitable capability query is `@media (hover: hover) and (pointer: fine)`.

Always provide a useful touch/press state separately. Hover must never be the only indication that something is interactive.

## Implementation guardrail

These recipes are interaction patterns, not instructions to adopt a particular animation library.

- Prefer existing CSS and project primitives.
- Use an already-installed advanced motion capability when dynamic or gesture-driven behavior requires it.
- Do not introduce or replace a dependency merely to follow a recipe.
- Preserve existing component, routing, state, styling, and data architecture.