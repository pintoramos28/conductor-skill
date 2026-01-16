---
name: context-driven-dev
description: "Use for context-driven development workflows: establishing project context, creating tracks/specs/plans, implementing tasks via a defined workflow, checking status, and reverting work. Applies when users mention context-driven development, specification-driven development, tracks, spec.md/plan.md, workflow-driven execution, or a project context index."
license: Apache-2.0
metadata:
  author: "pintoramos28"
  revision: "1.0.0"
---

# Context-Driven Development

## Core idea

Treat project context as versioned artifacts. Follow a disciplined lifecycle: **Context → Spec & Plan → Implement**, with explicit user checkpoints.

## What to load first

1. Read the project’s context index (if any) to locate context artifacts.
2. Use the command protocols in this skill’s `references/commands-*.md` files as the source of truth.

## Command map (protocol references)

- `setup` → `references/commands-setup.md`
- `newTrack` → `references/commands-newTrack.md`
- `implement` → `references/commands-implement.md`
- `status` → `references/commands-status.md`
- `revert` → `references/commands-revert.md`

## Universal File Resolution Protocol (summary)

When asked for any context-driven artifact (product definition, tech stack, plan, spec, etc.), resolve it via **index files** first.

1. **Project context**: a project-level context index (e.g., `context/index.md`).
2. **Track context**: read the tracks registry, find the track’s link, then use `<track>/index.md`.
3. **Fallbacks** (use when index is absent):
   - Project: `context/product.md`, `context/product-guidelines.md`, `context/tech-stack.md`, `context/workflow.md`, `context/tracks.md`, `context/tracks/`.
   - Track: `context/tracks/<track_id>/spec.md`, `context/tracks/<track_id>/plan.md`, `context/tracks/<track_id>/metadata.json`.
4. Verify paths exist on disk before use.

If a user references “the plan,” prefer the tracks registry or the current track’s `plan.md` when a track is in scope.

## Behavioral requirements from provided prompts (high‑priority)

- **Validate every tool call**; on failure, stop and ask for instructions.
- **Ask questions sequentially** when prompts require interactive steps.
- **Use the workflow file** as the source of truth for task execution and plan structure.
- **Always update plan/tracks statuses** as specified in the prompts.
- **When generating plans**, include `[ ]` markers on every task and sub-task, and inject the phase completion meta‑task if the workflow defines it.
- **Do not proceed** when setup prerequisites are missing; instruct user to run `/context:setup`.

## Templates and reference files (if present)

Use the bundled assets as the default templates when the repo does not supply its own:

- Workflow template: `assets/workflow.md`
- Code styleguides: `assets/code_styleguides/*.md`

## Bundled references

Use these reference files for full fidelity instructions (load only when needed):

- [references/context-driven-overview.md](references/context-driven-overview.md) — concise overview of context-driven development purpose and lifecycle.
- [references/commands-setup.md](references/commands-setup.md) — full setup protocol (generic).
- [references/commands-newTrack.md](references/commands-newTrack.md) — full new track protocol (generic).
- [references/commands-implement.md](references/commands-implement.md) — full implement protocol (generic).
- [references/commands-status.md](references/commands-status.md) — full status protocol (generic).
- [references/commands-revert.md](references/commands-revert.md) — full revert protocol (generic).
- [references/defaults.md](references/defaults.md) — default paths, command prefix, and index content for standalone use.

## Default conventions (fixed)

Always use the defaults in `references/defaults.md` for paths and command names. Do not substitute repo-specific values or rename paths.
