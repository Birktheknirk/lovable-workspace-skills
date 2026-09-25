---
name: ui-review
description: Audit an existing web interface for visual polish, interaction quality, accessibility, responsiveness, and consistency. Use when reviewing a page, feature, component, or recent UI work and the goal is to find the highest-value improvements without rewriting the application architecture.
---

# UI Review

Review the existing interface before changing it. Focus on the user experience and keep the project's architecture intact.

## Technology boundary

Do not introduce, remove, or replace technologies during a UI review unless the user explicitly asks for a technology change.

Do not turn a visual review into an architectural refactor.

## Review order

Inspect:

1. visual hierarchy
2. spacing and alignment
3. typography
4. component consistency
5. interaction and state feedback
6. motion
7. accessibility
8. responsive/mobile behavior
9. loading, empty, and error states
10. unnecessary visual complexity

## Review method

For every issue, explain:

- what is currently happening
- what should change
- why the change improves the user experience
- the smallest practical implementation approach

Prioritize issues that users will notice repeatedly over rare cosmetic details.

## Required output for code reviews

When reviewing code, use this table format:

| Current | Recommended | Why |
| --- | --- | --- |
| Current implementation or behavior | Concrete improvement | Short rationale |

Keep recommendations implementation-ready but avoid introducing new dependencies.

## Visual review

Look for:

- inconsistent spacing
- arbitrary radii
- weak hierarchy
- too many borders or shadows
- ambiguous primary actions
- missing hover/focus/pressed/disabled states
- abrupt state changes
- over-animated high-frequency interactions
- mobile overflow or unreachable controls
- content hidden behind fixed UI

## Final pass

After the proposed changes, verify that the result still feels like the same product: improved and more coherent, not redesigned into a different design language without being asked.
