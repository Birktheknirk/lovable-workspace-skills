---
name: prototype
description: Explore multiple genuinely different UI directions for a product feature before committing to one. Use when the user is unsure about layout, hierarchy, interaction pattern, navigation, or visual treatment and wants to compare distinct approaches inside the existing application.
---

# UI Prototyping

Use prototypes to reduce uncertainty before polishing a single direction.

## Technology boundary

Prototype within the project's existing stack and component system.

- Do not add dependencies just to prototype a visual idea.
- Do not create a parallel production architecture for temporary exploration.
- Reuse existing components, tokens, and project patterns where practical.
- Keep mocked data local and clearly isolated when the task is visual exploration.
- Do not modify production data, backend behavior, routing, or authentication solely for a prototype.

## Core principle: divergence

The value of a prototype is comparison.

Create genuinely different directions rather than cosmetic variations. A useful set changes a meaningful design axis such as:

- information hierarchy
- layout structure
- density
- navigation
- interaction model
- primary-action emphasis
- persistence versus context

Keep the underlying user task and product intent constant so the differences are easy to evaluate.

## Scope

Prototype one focused UI problem at a time.

If a request covers a large feature or page, identify the highest-leverage interaction or surface to explore rather than prototyping the entire product at once.

State the brief in one sentence before implementation:

- what is being explored
- where it belongs
- what the user must be able to accomplish

## Explore before polishing

Default to 3 directions.

Each direction should:

- have a distinct name
- differ on a named design axis
- use realistic product-shaped content
- be functional enough to judge
- use the existing design language and components
- avoid spending time on details that do not affect the decision

Do not create multiple variants that differ only by color, copy, or tiny spacing changes.

## Isolate exploration

Keep experimental UI isolated from production behavior.

In an existing application:

- prefer a dedicated prototype route, page, or isolated surface using the project's normal routing mechanism
- keep prototype-only components separate and clearly identifiable
- do not import prototype-only code into production features before a direction is selected
- do not create duplicate global systems for the prototype
- remove abandoned prototype branches after the decision

## Realism

A prototype should be realistic enough to reveal design problems.

Use realistic labels, plausible content lengths, representative data, actual product states, and real interactions where they affect the decision.

Avoid lorem ipsum when real content is available, dead buttons for interactions that matter, and placeholder layouts that conceal responsive or hierarchy issues.

Mock only what is necessary to explore the visual or interaction question.

## Comparison

Present each direction with:

| # | Variant | Axis | When it fits | Main tradeoff |
| --- | --- | --- | --- | --- |
| 1 | Quiet | Reduced visual emphasis | Daily-use workflows | Less expressive |
| 2 | Editorial | Strong hierarchy and whitespace | High-context moments | Uses more space |
| 3 | Dense | Information-first layout | Frequent scanning | Higher cognitive load |

Do not choose a direction on the user's behalf. Explain the meaningful tradeoffs and let the user decide.

## Prototype picker

When several directions need to be compared interactively, use the reusable picker pattern in [PICKER.md](PICKER.md).

The picker is exploration chrome, not part of the product design.

Requirements:

- show one variant at a time at a useful size
- make switching immediate
- provide mouse/touch and keyboard-friendly navigation where appropriate
- keep the picker visually distinct from the product
- do not let picker UI obscure the prototype being evaluated
- do not animate the variant swap itself; comparison should feel immediate

Use the project's existing routing and component conventions to mount the prototype. Do not introduce a new framework or component library just to build the picker.

## Verification

Before presenting the prototype:

1. Confirm every variant renders.
2. Confirm meaningful interactions work.
3. Check responsive behavior at relevant widths.
4. Check the browser console for obvious errors.
5. Confirm prototype code has not changed production data or architecture.
6. Compare the variants at realistic scale, not only as tiny thumbnails.

## After selection

Once the user selects a direction:

- integrate only the selected direction
- follow the existing application's architecture and conventions
- reuse production components and tokens
- remove abandoned prototype code and picker chrome unless the user explicitly asks to keep it
- do not carry exploratory alternatives into production

If the user wants another round, keep the prototype surface and create a new set that meaningfully diverges around the chosen direction.

## Technology-safe output

Prototyping is a design exploration workflow, not a reason to change technology.

Never introduce a dependency, framework, routing system, state library, styling system, or backend service solely to make a prototype more convenient.