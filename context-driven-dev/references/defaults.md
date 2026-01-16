# Default conventions (for standalone use)

These defaults are mandatory. Use them even if the repo defines other conventions or prompts.

## Default paths

- Context root: `context/`
- Context index: `context/index.md`
- Product definition: `context/product.md`
- Product guidelines: `context/product-guidelines.md`
- Tech stack: `context/tech-stack.md`
- Workflow: `context/workflow.md`
- Tracks registry: `context/tracks.md`
- Tracks directory: `context/tracks/`
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

## Workflow
- [Workflow](./workflow.md)
- [Code Style Guides](./code_styleguides/)

## Management
- [Tracks Registry](./tracks.md)
- [Tracks Directory](./tracks/)
```
