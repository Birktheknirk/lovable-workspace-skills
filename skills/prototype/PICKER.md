# Prototype Picker

Use this as a reusable interaction pattern for comparing prototype variants. Keep the picker visually separate from the product UI.

## Behavior

- Show one variant at a time at a useful viewing size.
- Provide one control per variant.
- Indicate the active variant with a clear selected state.
- Switching variants should be immediate.
- Support keyboard navigation when the prototype is used on desktop.
- Do not block interaction while prototype content is animating.
- Keep the picker out of the product's information hierarchy.
- Move the picker when it would cover an important part of the prototype.

## Keyboard behavior

Recommended defaults:

- Number keys 1-9 select the corresponding variant.
- ArrowRight moves to the next variant.
- ArrowLeft moves to the previous variant.
- Ignore global shortcuts while the user is typing in an input, textarea, select, or contenteditable element.

Only expose shortcuts that are useful for the number of variants being shown.

## Visual behavior

The picker should read as development/exploration chrome.

Prefer:
- compact footprint
- strong contrast against the prototype
- clear selected state
- accessible focus state
- minimal decoration
- fixed placement when it does not obscure the work

Do not let the picker establish the design language of the product being evaluated.

## Implementation

Use the project's existing components and styling primitives.

In a React application, model the active variant with the project's normal state mechanism and render one keyed variant at a time when remounting is useful for replaying entrance behavior.

The picker itself should not require a new library, route system, or state architecture.

## Verification

Before presenting the prototype:

- switch through every variant
- verify keyboard navigation if enabled
- verify the selected state
- verify the picker does not cover important content
- verify responsive behavior
- verify the prototype remains isolated from production behavior