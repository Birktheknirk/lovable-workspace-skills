---
name: apple-ui
description: Create calm, premium, Apple-inspired web interfaces through hierarchy, restraint, typography, spacing, tactile feedback, material-like depth, and fluid interaction. Use when a product should feel polished, minimal, spacious, and highly intentional rather than visually busy.
---

# Apple-Inspired UI

Use Apple design principles as a reference for clarity, hierarchy, restraint, physicality, and craft—not as a literal visual clone.

## Technology boundary

Change the interface, not the application's technology stack.

- Reuse the project's existing components, styling primitives, tokens, and interaction capabilities.
- Do not introduce or replace a UI library, animation framework, routing system, state library, CSS framework, or backend technology to achieve an Apple-like result.
- Prefer the simplest capability already available in the project.
- Do not add dependencies merely to achieve visual polish.
- If a design pattern appears to require a technology change, adapt the pattern to the existing project instead.

## Design principles

### Clarity

Make the primary task, current state, and information hierarchy obvious. Reduce anything that competes with the user's attention.

### Deference

Let content and actions carry the visual weight. Use decoration only when it improves hierarchy, meaning, feedback, or orientation.

### Depth

Create spatial hierarchy with contrast, spacing, restrained elevation, and carefully used translucency. Depth should explain what is above, below, or floating over something else.

### Consistency

Related components should look and behave alike. Similar interactions should use similar feedback and spatial behavior.

### Feedback

A meaningful action should be acknowledged immediately. Feedback should communicate the result without becoming visual noise.

### Restraint

Prefer one strong visual decision over several competing effects. Premium UI often comes from removing rather than adding.

### Agency

Keep users in control. Avoid unnecessary confirmation steps, forced paths, or interaction patterns that make the interface feel controlling.

### Familiarity

Use recognizable interaction patterns and specific labels. Break conventions only when there is a clear user benefit.

### Flexibility

Respect different devices, input methods, text sizes, and accessibility needs. Adapt the interaction model when the context changes instead of merely shrinking the desktop layout.

### Craft

Treat typography, spacing, alignment, states, and transitions as deliberate parts of one system. Small inconsistencies accumulate into visible roughness.

### Delight

Use delight as a result of good execution, not decoration added on top. Avoid novelty that competes with the task.

## Visual guidance

Prefer:

- purposeful whitespace
- strong typographic hierarchy
- consistent spacing and corner treatment
- restrained accents
- subtle separators where separation is needed
- soft depth instead of heavy shadows
- clear primary versus secondary actions
- compact but comfortable controls
- surfaces that communicate real spatial hierarchy

Avoid:

- excessive glassmorphism
- giant blurred gradients behind ordinary application UI
- gratuitous glow effects
- every element being rounded into a pill
- excessive cards nested inside cards
- badges and outlines used as decoration
- using color as the only way to establish hierarchy

## Typography

Treat typography as part of the layout system.

- Use size, weight, line height, and tracking together.
- Give large headings tighter leading and tracking where appropriate.
- Keep body text comfortable to read.
- Use secondary text to support the primary hierarchy rather than compete with it.
- Respect the project's existing font and design tokens before introducing a new typeface.

## Surfaces and materials

Use material-like treatment only when it communicates hierarchy.

- Start with spacing and contrast.
- Add a subtle border or shadow when necessary.
- Add blur or translucency only when a floating relationship benefits from it.
- Keep text legible over translucent surfaces.
- Do not apply glass treatment indiscriminately.

## Motion

Motion should reinforce spatial continuity, direct manipulation, feedback, or state changes.

- Use the existing project's animation capabilities.
- Keep ordinary UI motion restrained and responsive.
- Make anchored surfaces feel related to their trigger.
- Keep dialogs distinct from anchored popovers.
- Respect reduced-motion preferences.

Detailed motion implementation belongs to the separate `animation` skill; do not duplicate its complete rules here.

## Before changing an interface

Inspect the existing implementation first:

- reuse existing components
- reuse existing design tokens
- preserve established spacing and typography
- preserve familiar workflows
- improve the visual language before introducing new patterns

For concrete patterns, consult [RECIPES.md](RECIPES.md).

## Final check

Before considering the work complete:

1. Is the primary task obvious?
2. Is anything visually louder than it needs to be?
3. Do related elements behave consistently?
4. Does depth clarify hierarchy rather than decorate?
5. Does the interface still feel like the same product?
6. Could one unnecessary visual element be removed without reducing clarity?
