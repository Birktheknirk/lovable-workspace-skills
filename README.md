# Lovable Workspace Skills

Reusable workspace skills for building polished, Apple-inspired web interfaces in Lovable.

## Purpose

This repository contains task-specific workspace skills that improve UI quality, interaction design, animation, mobile behavior, prototyping, and visual review.

The skills focus on how the interface should be designed and built, not on a specific application architecture.

## Technology safety

These skills must work with the application's existing technology stack.

They should:
- reuse existing components, tokens, utilities, and platform capabilities
- avoid unnecessary dependencies
- avoid replacing frameworks, routers, state systems, styling systems, or backend technologies
- preserve the existing application architecture when making UI improvements

Project-specific technology constraints belong in Lovable Project Knowledge, not in these reusable workspace skills.

## Skills

| Skill | Purpose |
| --- | --- |
| design-engineering | General UI quality, hierarchy, interaction, and polish |
| apple-ui | Apple-inspired clarity, restraint, depth, typography, and craft |
| animation | Purposeful motion, timing, easing, and interaction behavior |
| mobile-native | Native-feeling mobile web and touch behavior |
| ui-review | Structured review and prioritization of UI improvements |
| prototype | Exploration of genuinely different UI directions |

Each skill contains a SKILL.md entrypoint and may contain supporting files such as RECIPES.md or other references when they materially improve the workflow.

## Design philosophy

The goal is not to make every interface look like Apple.

The goal is to apply qualities associated with strong Apple interface work:
- clarity
- restraint
- hierarchy
- consistency
- direct feedback
- thoughtful motion
- strong typography
- spatial coherence
- accessibility
- careful attention to detail

## Usage

Install the individual skill folders in the Lovable workspace as needed.

Use the most specific skill relevant to the task. Skills may be combined when their responsibilities are complementary.

## Repository structure

    skills/
    ├── animation/
    ├── apple-ui/
    ├── design-engineering/
    ├── mobile-native/
    ├── prototype/
    └── ui-review/

Supporting files live inside the skill they belong to.

## Relationship to Project Knowledge

Workspace Skills provide reusable workflows and design guidance.

Project Knowledge defines the specific application's permanent constraints, including its technology stack, architecture, design tokens, component conventions, and database conventions.

Keeping these layers separate allows the skills to remain reusable while still respecting the technology decisions of each Lovable project.