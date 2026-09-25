---
name: design-engineering
description: Improve the quality, polish, and interaction design of web interfaces. Use when building or refining application UI, components, states, or interactions and the goal is to make the product feel intentional, responsive, refined, and production-quality.
---

# Design Engineering

Improve the interface without changing the product architecture.

## Technology boundary

Treat the existing application stack as fixed unless the user explicitly requests a technology change.

- Do not introduce a new framework or competing library for a UI problem.
- Do not replace the existing component system, router, state system, styling system, or data layer.
- Prefer existing components, tokens, utilities, and patterns already present in the project.
- Do not add dependencies merely to implement visual polish.
- If a design pattern appears to require a technology change, adapt it to the existing project instead.

## Design posture

Build interfaces that feel calm, deliberate, responsive, and cohesive.

Prioritize:

- clear visual hierarchy
- strong spacing and alignment
- typography that supports hierarchy rather than decoration
- restrained use of color, borders, shadows, and gradients
- obvious interaction states
- consistent component behavior
- meaningful empty, loading, success, and error states
- visual continuity between related states

Avoid:

- decorative UI with no purpose
- excessive borders, shadows, gradients, or rounded containers
- too many competing focal points
- inconsistent spacing or component variants
- generic placeholder-looking states when the product has enough context to make them specific

## Interaction quality

Every interactive control should communicate:

1. what can be interacted with
2. what happens when it is pressed, focused, hovered, or disabled
3. what state it is currently in

Feedback should happen as early as the interaction model allows. Press feedback should feel immediate rather than waiting for a full click cycle.

Use motion when it improves orientation, feedback, continuity, or perceived responsiveness. Do not animate purely because an animation is available.

## Before changing UI

Inspect the existing implementation and identify:

- reusable components
- existing design tokens
- established spacing and typography patterns
- existing interaction conventions
- existing responsive behavior

Extend those patterns before creating new ones.

When a concrete pattern is needed, consult [RECIPES.md](RECIPES.md) and adapt the relevant recipe to the existing product.

## Quality bar

A finished interface should look coherent at first glance and still hold up when inspecting small details: alignment, focus states, transitions, loading behavior, keyboard use, and mobile behavior.
