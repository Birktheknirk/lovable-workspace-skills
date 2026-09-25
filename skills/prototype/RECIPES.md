# Prototype Recipes

## 1. Three-direction exploration

Use when the user knows the feature but not the best UI structure.

Create three directions that differ on real axes:

- Quiet: minimal emphasis and low visual noise
- Editorial: stronger typography and whitespace
- Dense: information-first and compact

Keep content and the core task constant.

## 2. Layout divergence

Use when several layouts could support the same task.

Change the information structure rather than only styling: sidebar versus contextual controls, stacked sections versus split layout, or persistent actions versus contextual actions.

Keep the interaction semantics understandable in every direction.

## 3. Interaction divergence

Use when the question is how a task should be performed.

Compare distinct interaction models, for example modal workflow, side sheet, or inline expansion.

Do not present three visual skins of the same interaction as separate concepts.

## 4. Density divergence

Use when the main uncertainty is how much information should be visible at once.

Compare spacious, balanced, and compact treatments using realistic content.

## 5. Prototype picker

Use when the user needs to flip between directions in a working prototype.

Use [PICKER.md](PICKER.md) as the reference behavior. Keep the picker separate from the product design and make variant switching immediate.

## 6. Prototype-to-production handoff

Use when a direction has been selected.

Before integration:

1. Identify which prototype components map to existing production components.
2. Move only the selected interaction and visual treatment into production.
3. Remove prototype-only wrappers, mocks, picker chrome, and alternative variants.
4. Re-check responsive behavior and accessibility in the production context.
5. Confirm no new dependency was added solely for exploration.

## Technology boundary

Recipes describe exploration methods, not technology choices.

- Reuse the existing stack.
- Reuse existing components and tokens.
- Keep prototype-only data local.
- Do not introduce temporary dependencies unless the user explicitly approves a technology change.