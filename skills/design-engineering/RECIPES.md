# Design Engineering Recipes

Use these recipes as concrete starting patterns when improving UI. Adapt them to the existing product, components, content, and design system rather than applying them mechanically.

## 1. Calm the visual hierarchy

**Use when:** A screen feels busy or several elements compete for attention.

1. Identify the single most important task or piece of information.
2. Give that element the clearest typographic and spatial emphasis.
3. Reduce competing borders, fills, badges, shadows, and accent colors.
4. Group secondary information through spacing and typography before adding containers.
5. Check the screen again at a glance: the eye should know where to start.

**Avoid:** Solving hierarchy problems by making everything larger, darker, bolder, or more colorful.

---

## 2. Refine a dense dashboard

**Use when:** A dashboard has useful information but feels heavy or cluttered.

- Establish a clear top-to-bottom hierarchy.
- Group related metrics instead of giving every metric its own visual container.
- Use consistent column alignment and spacing.
- Keep supporting labels quieter than primary values.
- Prefer one strong emphasis per section.
- Preserve important density; do not add whitespace that harms scanning.

**Quality check:** A user should be able to identify the key number, its context, and the next useful action without visually decoding the whole page.

---

## 3. Improve a form

**Use when:** A form works functionally but feels awkward or visually inconsistent.

1. Group fields that belong to the same decision.
2. Make labels and supporting text easy to scan.
3. Keep related controls visually close.
4. Make validation feedback appear next to the relevant field.
5. Give submit, cancel, disabled, focus, and error states clear treatment.
6. Avoid adding extra containers when spacing already provides grouping.

**Quality check:** Users should understand what is required, what went wrong, and what to do next without hunting through the form.

---

## 4. Refine a data table

**Use when:** A table is difficult to scan or feels overly boxed in.

- Establish a strong header hierarchy.
- Align numeric values consistently.
- Use spacing and typography before heavy borders.
- Keep row states subtle but visible.
- Make the primary row action discoverable without adding permanent visual noise.
- Preserve horizontal scrolling or responsive behavior when the data genuinely requires it.

**Avoid:** Turning every cell, row, and action into a separate card.

---

## 5. Make an interactive control feel tactile

**Use when:** A button, toggle, menu trigger, or other pressable element feels inert.

1. Make hover feedback available where hover is actually supported.
2. Provide a clear focus state for keyboard users.
3. Add immediate pressed feedback.
4. Keep the movement subtle enough that the control still feels stable.
5. Ensure disabled states remove ambiguity without making the control disappear.

**Default:** Small transform or opacity changes are usually enough. Do not add elaborate motion to high-frequency actions.

---

## 6. Improve a modal, popover, or sheet

**Use when:** An overlay feels disconnected from the action that opened it.

- Preserve the existing overlay primitive.
- Keep dialogs centered unless the product intentionally uses another pattern.
- Make anchored popovers feel spatially connected to their trigger.
- Use enter/exit motion that is quick and easy to interrupt.
- Keep the underlying page visually subordinate without making it feel frozen or broken.
- Ensure focus moves into the surface and returns predictably.

**Avoid:** Rebuilding the overlay system just to achieve a different visual treatment.

---

## 7. Design better empty states

**Use when:** A screen has no data or no current results.

Use a simple hierarchy:

1. What is empty?
2. Why might it be empty?
3. What can the user do next?

Keep the state useful rather than decorative. Prefer a meaningful action over large illustrations or visual filler unless the product already uses them.

---

## 8. Design loading states

**Use when:** A screen waits for data.

- Preserve the final layout shape where practical.
- Avoid replacing the entire page with a generic spinner when the structure is known.
- Keep loading indicators proportional to the task.
- Do not animate every placeholder independently unless it helps the user understand the loading state.
- Preserve already-available content rather than unnecessarily blanking it.

**Goal:** Make waiting feel stable and predictable, not busy.

---

## 9. Refine error states

**Use when:** Something fails.

- Explain the problem in user language.
- Place the message near the affected action or content.
- Offer the next useful action when one exists.
- Preserve unaffected content and controls.
- Avoid dramatic visual treatment for routine errors.

**Goal:** Help the user recover, not merely announce failure.

---

## 10. Reduce visual noise without flattening the design

**Use when:** A page has too many borders, shadows, pills, badges, or surfaces.

Remove in this order:

1. Decorative elements with no task-related purpose.
2. Redundant containers.
3. Heavy borders that duplicate spacing.
4. Shadows that do not communicate depth.
5. Accent colors used only for emphasis that can be expressed through hierarchy.

Then reassess spacing and typography. Removing decoration often exposes a stronger underlying layout.

---

## 11. Improve a repeated list interaction

**Use when:** Items are added, removed, expanded, or reordered.

- Prefer transitions that can retarget smoothly if state changes again.
- Keep motion short enough that the user can continue interacting.
- Use small staggered entrance delays only when they improve comprehension or initial orientation.
- Never block interaction until decorative motion finishes.
- Keep enter and exit motion spatially consistent.

---

## 12. Polish without redesigning

**Use when:** A working feature needs refinement, not a new concept.

Work in this order:

1. Fix hierarchy.
2. Fix spacing and alignment.
3. Fix component consistency.
4. Fix interaction states.
5. Add or refine motion where it communicates something useful.
6. Remove unnecessary decoration.
7. Re-check responsive behavior and accessibility.

**Rule:** Prefer a small number of high-impact changes over a large visual rewrite.

---

## Implementation guardrail

These recipes describe UI and interaction patterns, not a technology stack.

Before implementation:

- Reuse the project's existing components and tokens.
- Follow the project's established styling and routing patterns.
- Do not introduce a dependency just to use a recipe.
- Do not replace an existing component, library, or architectural pattern for visual polish alone.
- If a recipe appears to require a technology change, adapt the recipe to the existing project instead.
