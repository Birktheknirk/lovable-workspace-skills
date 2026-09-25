# Apple UI Recipes

Use these recipes as concrete design patterns. Adapt them to the existing application rather than applying them mechanically.

## 1. Establish a calm hierarchy

**Use when:** A screen feels busy or the primary task is unclear.

1. Identify the primary task or most important information.
2. Give it the strongest combination of size, weight, contrast, and space.
3. Reduce competing accents, badges, borders, and containers.
4. Use spacing and typography to create secondary grouping before adding decoration.
5. Check the screen at a glance: the intended starting point should be obvious.

**Avoid:** Making every element prominent.

---

## 2. Simplify a card-heavy interface

**Use when:** The page is made of many bordered or elevated cards.

- Remove containers that do not communicate a real grouping.
- Use spacing to separate related sections when a boundary is unnecessary.
- Reserve elevation for surfaces that genuinely sit above another surface.
- Avoid stacking multiple layers of cards unless the hierarchy requires it.
- Keep one clear surface hierarchy instead of treating every block as a floating object.

**Goal:** Make the interface feel lighter without removing useful structure.

---

## 3. Create an Apple-like surface hierarchy

**Use when:** You need depth without visual heaviness.

Use the smallest amount of treatment that establishes spatial hierarchy:

1. Background
2. Content surface
3. Elevated or floating surface
4. Focused interactive surface

Prefer subtle contrast, restrained shadow, and spacing before blur or translucency.

When using translucency, maintain text legibility and avoid stacking multiple translucent layers.

---

## 4. Refine primary and secondary actions

**Use when:** A screen has too many visually competing actions.

- Give one action the clearest emphasis.
- Keep secondary actions quieter but still discoverable.
- Use destructive styling only when the action is genuinely destructive.
- Avoid making every action a filled button.
- Keep action placement consistent with the surrounding product.

**Goal:** The user should know the intended next action without being forced into it.

---

## 5. Make controls feel tactile

**Use when:** Buttons, toggles, menus, or other controls feel visually static.

- Provide clear hover feedback only where hover is supported.
- Provide immediate pressed feedback.
- Preserve a strong keyboard focus state.
- Use subtle transforms or opacity changes rather than large movement.
- Keep disabled states unmistakable.

The feedback should reinforce the action, not become the action.

---

## 6. Make overlays feel spatially connected

**Use when:** A popover, menu, drawer, or sheet feels disconnected from its trigger.

- Keep the relationship to the triggering control visually obvious.
- Use an origin and movement direction that match the entry point.
- Keep centered dialogs centered rather than treating them like anchored popovers.
- Use quick, restrained transitions.
- Preserve predictable dismissal and focus behavior.

**Avoid:** Using the same motion treatment for every type of overlay.

---

## 7. Design a quiet empty state

**Use when:** A screen contains no data or no current results.

Structure the state around:

- a clear explanation of what is empty
- useful context when necessary
- one obvious next action

Avoid large decorative illustrations or excessive copy when they do not help the task.

---

## 8. Build a confident loading state

**Use when:** A page waits for data.

- Preserve the expected layout shape when possible.
- Prefer contextual placeholders over a generic full-page spinner.
- Do not make every skeleton element pulse independently.
- Keep existing content visible when it remains valid.
- Use motion sparingly so loading feels stable rather than busy.

---

## 9. Improve typography hierarchy

**Use when:** A screen feels visually weak even though its components are correct.

Treat typography as a system:

- use size and weight together
- keep display text tighter than body text
- give body text comfortable line height
- use secondary text for supporting information, not primary decisions
- maintain consistent text hierarchy across related components

Avoid solving hierarchy problems with color alone.

---

## 10. Refine navigation and wayfinding

**Use when:** Users may not immediately understand where they are or where to go next.

Make sure the interface communicates:

- current location
- available destinations
- current context
- a predictable way back

Prefer familiar navigation patterns and specific labels over vague categories.

---

## 11. Make mobile actions reachable

**Use when:** A desktop layout has been adapted to mobile.

- Keep primary actions within comfortable reach.
- Prefer sheets or bottom-oriented surfaces when the task benefits from them.
- Avoid placing critical actions where fixed browser or device UI can obstruct them.
- Preserve the same hierarchy as desktop while adapting the interaction model.
- Do not simply shrink desktop controls and call the result mobile-ready.

---

## 12. Add depth without "glass everywhere"

**Use when:** You want a premium visual treatment.

Start with:

1. contrast
2. spacing
3. subtle shadow
4. border or separator
5. only then translucency/blur if it genuinely improves the hierarchy

Use glass-like treatment for functional floating surfaces rather than ordinary content blocks.

**Avoid:** Generic glassmorphism applied to every card, section, or background.

---

## 13. Polish without redesigning the product

**Use when:** The product works and needs a higher visual bar.

Work in this order:

1. Clarify hierarchy.
2. Fix spacing and alignment.
3. Refine typography.
4. Simplify surfaces and decoration.
5. Improve states and feedback.
6. Add purposeful motion.
7. Re-check responsive and accessibility behavior.

Keep the user's familiar workflow unless a redesign was explicitly requested.

---

## 14. Remove one unnecessary thing

**Use when:** A polished screen still feels slightly busy.

Ask:

> What can be removed without reducing clarity or functionality?

Try removing one:

- border
- badge
- redundant heading
- unnecessary container
- decorative icon
- secondary action
- shadow
- repeated label

Then re-check the hierarchy before removing anything else.

---

## Technology boundary

These recipes define visual and interaction decisions only.

- Reuse the project's existing components, tokens, CSS, and interaction primitives.
- Do not introduce a new library to implement a recipe.
- Do not replace an existing library or architectural pattern for visual reasons alone.
- If a pattern conflicts with the project's technology constraints, preserve the technology constraints and adapt the visual treatment.
