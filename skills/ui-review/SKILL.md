---
name: ui-review
description: Audit an existing web interface for visual polish, interaction quality, accessibility, responsiveness, and consistency. Use when reviewing a page, feature, component, or recent UI work and the goal is to find the highest-value improvements without rewriting the application architecture.
---

# UI Review

Review the existing interface before changing it. Focus on user experience, visual quality, accessibility, and responsive behavior while preserving the project's architecture.

## Technology boundary

- Do not introduce, remove, or replace technologies during a UI review unless the user explicitly requests a technology change.
- Do not turn a visual review into an architectural refactor.
- Prefer existing components, tokens, utilities, and patterns.
- If a recommendation appears to require a new dependency, first look for an existing project capability that solves it.

## Review process

Follow this order:

1. Understand the user's primary task and the page's role.
2. Inspect the existing implementation and identify reusable patterns.
3. Review visual hierarchy, spacing, typography, and surface treatment.
4. Review component consistency and interaction states.
5. Review motion and responsive behavior.
6. Review accessibility and state completeness.
7. Identify unnecessary visual complexity.
8. Prioritize the smallest set of high-value changes.

Do not redesign the product simply because a different layout could look interesting. Review against the product's existing intent and workflow.

## Review dimensions

### Visual hierarchy

Check whether the interface clearly communicates:
- what matters most
- what is actionable
- what is secondary
- where the user is and what context they are in

Look for weak hierarchy caused by excessive emphasis rather than missing decoration.

### Spacing and alignment

Check:
- consistency of spacing
- alignment across repeated elements
- section rhythm
- control grouping
- accidental gaps or crowding

Prefer the project's existing spacing system.

### Typography

Check:
- heading hierarchy
- text weight
- line height
- tracking where relevant
- readability of secondary information
- consistency across similar surfaces

Do not introduce a new typeface during a normal UI review.

### Components and states

Check whether similar components look and behave consistently.
Review relevant states such as:
- default
- hover
- focus
- pressed/active
- selected
- disabled
- loading
- empty
- error

### Motion

Ask whether each animation:
- has a clear purpose
- matches the interaction frequency
- feels responsive
- preserves spatial continuity
- can handle rapid state changes
- respects reduced motion

For detailed animation implementation, use the separate `animation` workspace skill.

### Responsive and mobile behavior

Check:
- layout adaptation
- horizontal overflow
- clipped content
- fixed/sticky overlap
- action reachability
- information density
- whether the interaction model needs to change on smaller screens

For deeper touch, viewport, and browser-platform issues, use `mobile-native`.

### Accessibility

Check:
- keyboard navigation
- visible focus
- semantic labels
- contrast
- non-color-only status
- reduced motion
- meaningful control states
- content selection where appropriate

Fix obvious accessibility failures before decorative polish.

## Prioritization

Classify findings by user impact:

- **High:** blocks, confuses, repeatedly slows, or materially degrades the primary workflow.
- **Medium:** noticeable inconsistency or friction that does not block the task.
- **Low:** cosmetic refinement with limited user impact.

Do not inflate severity for visual preference. Use High for user-facing problems, not for taste disagreements.

Prioritize recurring and workflow-critical issues over rare cosmetic details.

## Required output

For a review, return:

### Findings

Use one markdown table:

| Priority | Current | Recommended | Why |
| --- | --- | --- | --- |
| High | Current behavior or implementation | Smallest practical improvement | User-facing benefit |

Use one row per finding. Keep recommendations concrete enough to implement.

### Summary

After the table, give a brief summary of the main patterns found and the recommended order of work.

Do not provide a numeric overall score or rank the product itself.

## Recipes

For recurring review patterns, consult [RECIPES.md](RECIPES.md). Use the relevant recipe as a starting point and adapt it to the existing interface.

## Final check

Before recommending changes, verify:

1. The recommendation solves a real user-experience issue.
2. The recommendation fits the existing product language.
3. The smallest practical change is preferred.
4. Accessibility and responsive implications were considered.
5. No unnecessary technology change is being proposed.