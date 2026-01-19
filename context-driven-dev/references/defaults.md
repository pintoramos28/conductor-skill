# Default conventions (for standalone use)

These defaults are mandatory. Use them even if the repo defines other conventions or prompts.

## Default paths

- Context root: `context/`
- Context index: `context/index.md`
- Product definition: `context/product.md`
- Product guidelines: `context/product-guidelines.md`
- Tech stack: `context/tech-stack.md`
- Workflow: `context/workflow.md`
- Project spec: `context/spec.md`
- Tracks registry: `context/tracks.md`
- Tracks directory: `context/tracks/`
- Requirements index: `context/requirements-index.md`
- Decision log (ADRs): `context/decisions.md`
- Track artifacts:
  - `context/tracks/<track_id>/spec.md`
  - `context/tracks/<track_id>/plan.md`
  - `context/tracks/<track_id>/metadata.json`
  - `context/tracks/<track_id>/index.md`

## Default command prefix

- Command prefix: `/context:`
- Command names: `setup`, `newTrack`, `implement`, `status`, `revert`
  - Example: `/context:setup`

## Default templates

- Templates root: `assets/`
- Workflow template: `assets/workflow.md`
- Code styleguide templates: `assets/code_styleguides/*.md`

## Default index content

```markdown
# Project Context

## Definition
- [Product Definition](./product.md)
- [Product Guidelines](./product-guidelines.md)
- [Tech Stack](./tech-stack.md)
- [Project Spec](./spec.md)
- [Requirements Index](./requirements-index.md)
- [Decision Log](./decisions.md)

## Workflow
- [Workflow](./workflow.md)
- [Code Style Guides](./code_styleguides/)

## Management
- [Tracks Registry](./tracks.md)
- [Tracks Directory](./tracks/)

## Draft-first rule (applies to all context artifacts)

- For every context artifact `context/<name>.md`, the draft version is `context/<name>.draft.md`.
- Drafts MUST be created and kept in sync during edits.
- Approved content MUST be written to the non-draft file (`context/<name>.md`), with the draft retained (or identical without the DRAFT header).
```
