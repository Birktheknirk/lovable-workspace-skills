---
name: prototype
description: Explore multiple UI directions for a product feature before committing to one. Use when the user is unsure about layout, hierarchy, interaction pattern, navigation, or visual treatment and wants to compare distinct approaches inside the existing application.
---

# UI Prototyping

Use prototypes to reduce uncertainty before polishing a single direction.

## Technology boundary

Prototype within the project's existing stack and component system.

- Do not add dependencies just to prototype a visual idea.
- Do not create a parallel architecture for temporary UI.
- Reuse existing components and tokens where practical.
- Keep mocked data local and clearly isolated when the task is visual exploration.

## Exploration method

Create 2-3 meaningfully different directions, not three cosmetic variations.

Vary dimensions such as:

- information hierarchy
- layout structure
- density
- navigation pattern
- emphasis of primary actions
- contextual versus persistent controls

Keep the content and core task constant so the differences are easy to compare.

## Quality bar

Each direction should be coherent enough to judge. Avoid spending time polishing details that do not affect the decision.

## Comparison

For each direction, summarize:

- the interaction model
- the strongest benefit
- the main tradeoff
- when it is most appropriate

Do not choose on the user's behalf. Make the differences visible so the user can choose.

## After selection

Once a direction is selected, remove exploratory branches and implement the chosen pattern cleanly within the existing application architecture.
