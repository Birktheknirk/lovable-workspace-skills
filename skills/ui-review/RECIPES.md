# UI Review Recipes

Use these review patterns to turn an existing UI into a more polished version without changing its architecture.

## 1. Hierarchy pass

**Use when:** The page feels busy or the primary task is hard to find.

- Identify the primary task or information.
- Check whether size, weight, contrast, and spacing consistently support that priority.
- Reduce competing accents, borders, badges, and containers before adding more emphasis.
- Verify that secondary information is visually quieter.

**Output:** Identify the highest-impact hierarchy issue first.

## 2. Spacing and alignment pass

**Use when:** The interface feels subtly messy despite using the right components.

- Look for inconsistent gaps between related elements.
- Check alignment across repeated rows, columns, controls, and sections.
- Prefer existing spacing tokens and established patterns.
- Fix structural spacing before decorative styling.

## 3. Typography pass

**Use when:** A screen feels weak, dense, or inconsistent.

- Check hierarchy across headings, labels, values, helper text, and metadata.
- Use size, weight, line height, and tracking together.
- Avoid using color as the only hierarchy mechanism.
- Preserve the project's existing type system unless a type change is explicitly requested.

## 4. Surface simplification pass

**Use when:** There are too many cards, borders, shadows, pills, badges, or effects.

Remove in roughly this order:
1. Decorative elements with no functional purpose.
2. Redundant containers.
3. Heavy borders that duplicate spacing.
4. Unnecessary shadows or elevation.
5. Excess accent colors.

Re-check hierarchy after each reduction.

## 5. Interaction-state pass

**Use when:** Controls work but feel unresponsive or inconsistent.

Check:
- hover where hover is actually supported
- focus for keyboard users
- pressed/active feedback
- disabled state
- selected state
- loading state

Related controls should use consistent feedback patterns.

## 6. Motion pass

**Use when:** The interface includes transitions or animated state changes.

Check:
- does the motion have a purpose?
- is it appropriate for interaction frequency?
- is the timing quick enough?
- does the element enter/exit along a coherent path?
- can the state change again without awkward interruption?
- is reduced motion handled?

For implementation-specific guidance, use the separate animation workspace skill rather than duplicating detailed motion rules here.

## 7. Responsive pass

**Use when:** Desktop and mobile layouts do not feel like the same product.

- Check content hierarchy rather than only element dimensions.
- Look for horizontal overflow and clipped content.
- Check fixed or sticky elements for overlap.
- Confirm controls remain reachable.
- Check whether desktop interaction patterns need mobile adaptation.

Use the mobile-native skill for deeper touch and browser-platform issues.

## 8. Accessibility pass

Check:
- keyboard navigation
- visible focus states
- semantic labels
- sufficient contrast
- non-color-only status communication
- reduced motion
- content remains selectable where appropriate
- interactive targets are understandable

Fix obvious accessibility problems before decorative polish.

## 9. State-completeness pass

Every important data-driven surface should be considered in:
- normal state
- loading state
- empty state
- error state
- disabled or unavailable state where relevant

Prefer contextual states over generic placeholders.

## 10. High-value-first review

When many issues exist, prioritize:
1. Problems that repeatedly slow or confuse users.
2. Problems visible in the primary workflow.
3. Inconsistencies repeated across many components.
4. Accessibility or responsive failures.
5. Cosmetic details.

Do not produce a long list of low-value polish suggestions when a few structural changes would have a larger impact.

## 11. Before/after recommendation pattern

For each concrete issue, describe:

| Current | Recommended | Why |
| --- | --- | --- |
| What users see or what the code currently does | The smallest practical improvement | The user-facing benefit |

Keep the recommendation implementation-ready but avoid prescribing a new dependency.

## 12. Technology-safe review

When a review reveals a limitation:
1. Check existing components and utilities first.
2. Check existing CSS and design tokens.
3. Check existing interaction primitives.
4. Only then consider whether a technology limitation actually exists.

Never turn a UI review into an unsolicited architecture migration.