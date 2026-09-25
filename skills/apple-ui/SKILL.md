---
name: apple-ui
description: Create calm, premium, Apple-inspired web interfaces through hierarchy, restraint, typography, spacing, tactile feedback, material-like depth, and fluid interaction. Use when a product should feel polished, minimal, spacious, and highly intentional rather than visually busy.
---

# Apple-Inspired UI

Use Apple's interface principles as a design reference, not as a literal visual clone.

## Technology boundary

Change the interface, not the application's technology stack.

- Use existing project components and styling primitives.
- Do not introduce a new UI library, animation framework, routing system, or state library to achieve an Apple-like result.
- Prefer CSS and existing project capabilities for visual refinement.
- Keep architecture and dependencies unchanged unless explicitly requested.

## Core principles

### Clarity
Make the primary action, current state, and information hierarchy obvious.

### Deference
The interface should support content rather than compete with it. Remove decoration that does not help the user's task.

### Depth
Use restrained layers of contrast, translucency, shadow, blur, and spacing where they help users understand what is above or below what.

### Consistency
Related controls should look and behave alike. Enter and exit paths should make spatial sense.

### Feedback
Actions should acknowledge the user immediately and visibly.

### Restraint
Prefer one strong visual decision over several medium-strength ones.

## Visual guidance

Prefer:

- generous but purposeful whitespace
- strong typographic hierarchy
- subtle separators instead of heavy borders
- soft depth instead of large drop shadows
- a limited accent palette
- consistent corner radii
- compact, tactile controls
- clear primary versus secondary actions

Avoid:

- excessive glassmorphism
- huge blurred gradients behind ordinary application UI
- gratuitous glow effects
- over-rounded every-in-a-pill interfaces
- card-on-card-on-card layouts
- visual noise created by too many outlines and badges

## Motion

Motion should make state changes understandable and interactions feel direct.

For gesture-driven interactions, favor behavior that can follow the user's input and be interrupted naturally. For ordinary UI transitions, use the simplest existing mechanism that produces a polished result.

Respect reduced-motion preferences.

## Typography

Treat typography as part of the layout system. Balance size, weight, line height, and tracking instead of compensating for weak hierarchy with decoration.

## Final check

Ask whether the screen could remove one more visual element without losing clarity. If yes, remove it.
