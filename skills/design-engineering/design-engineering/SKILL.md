---
name: design-engineering
description: Improve the quality, polish, and interaction design of web interfaces. Use when building, refining, or reviewing application UI and the goal is to make the product feel intentional, responsive, refined, and production-quality without changing the application's technology stack or architecture.
---

# Design Engineering

Improve the interface without changing the product architecture.

## Technology boundary

Treat the application's existing technology stack as fixed.

- Do not introduce, remove, replace, or recommend competing frameworks, libraries, routers, state-management systems, styling systems, or backend technologies as part of UI work.
- Do not add a dependency merely to achieve visual polish, animation, responsiveness, or accessibility when the existing stack can handle it.
- Reuse existing components, design tokens, utilities, and patterns before creating new ones.
- If a UI requirement genuinely cannot be implemented with the existing stack, surface the limitation rather than silently changing the stack.
- Do not change application architecture to solve a visual problem unless the user explicitly asks for an architectural change.

## Design posture

Make interfaces feel calm, deliberate, responsive, and cohesive.

Prioritize:

- clear visual hierarchy
- intentional spacing and alignment
- typography that creates hierarchy without decoration
- restrained use of color, borders, shadows, gradients, and blur
- obvious interaction states
- consistent component behavior
- useful empty, loading, success, and error states
- visual continuity between related states
- strong defaults that reduce unnecessary decisions

Avoid:

- decoration without a user-facing purpose
- excessive borders, shadows, gradients, blur, or glow
- too many competing focal points
- inconsistent spacing or one-off component variants
- dense layouts when whitespace would improve comprehension
- generic placeholder-looking states when the product context allows something more specific

## Build from the existing system

Before changing UI, inspect the existing implementation and identify:

- reusable components
- existing variants
- design tokens
- spacing and typography conventions
- existing responsive behavior
- established interaction patterns

Extend those patterns before creating a new one.

Do not rebuild an existing primitive just to make it look different. Style and compose the existing primitive instead.

## Interaction quality

Every interactive control should clearly communicate:

1. that it is interactive
2. what happens when it is pressed, focused, hovered, disabled, or loading
3. what state it is currently in

Feedback should feel immediate.

Use subtle press feedback for pressable controls where it improves tactility. Keep it restrained and consistent across similar controls.

Prefer interaction feedback that explains cause and effect rather than decorative motion.

## Motion decisions

Do not animate by default. First decide whether animation improves the interaction.

Use animation primarily for:

- feedback
- state changes
- spatial continuity
- orientation
- preventing abrupt visual changes
- occasional moments of delight where appropriate

For frequent actions, keep motion very short or omit it. For occasional overlays such as drawers, dialogs, and toasts, use restrained transitions.

Prefer the simplest mechanism already available in the project. For ordinary UI transitions, prefer CSS transitions when they are sufficient. Use more advanced animation capabilities only when the interaction genuinely requires dynamic, interruptible, or gesture-driven behavior and the project already supports that capability.

Respect reduced-motion preferences.

## Visual refinement

When polishing an existing screen, improve the highest-impact issues first:

1. hierarchy and layout
2. spacing and alignment
3. typography
4. component consistency
5. interaction states
6. motion and micro-interactions
7. secondary visual details

Do not add visual effects to compensate for weak structure.

## Quality bar

A finished interface should feel coherent at first glance and remain polished in details such as:

- alignment
- focus states
- hover and press states
- loading and disabled states
- transitions
- keyboard interaction
- responsive behavior
- mobile touch behavior
- empty and error states

Before considering the work complete, look for one unnecessary visual element, one inconsistent spacing or sizing decision, and one missing interaction state. Fix them when appropriate.
