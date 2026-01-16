# Context-Driven Development overview

Context-driven development structures work into a disciplined lifecycle:

**Context → Spec & Plan → Implement**

It treats context as versioned artifacts in the repo so every agent and teammate shares a single source of truth. Core ideas:

- Create and maintain project context files (product definition, tech stack, workflow, etc.).
- Create a **Track** for each feature or bug: a spec and an implementation plan.
- Implement by following the plan and workflow, updating plan statuses, and using explicit verification steps.
- Keep progress visible via the tracks registry.

Primary commands (names vary by repo):

- setup/init context
- create track (spec + plan)
- implement track (execute plan per workflow)
- status (summarize progress)
- revert (undo a track/phase/task with VCS awareness)
