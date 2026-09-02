# Backlog

Flat task list. Status values: `backlog` | `ready` | `in_progress` | `blocked` | `done` | `cancelled`.

On cleanup, move shipped work to [`CHANGELOG.md`](../CHANGELOG.md) and clean the backlog — see [`CLEANUP.md`](CLEANUP.md).

Reorder freely. Cancel by setting status to `cancelled`. Unexpected work becomes a new task with its own ID.

## Task IDs

`[external-tracker-id-]kebab-slug` — e.g. `explore-caching` (local) or `PROJ-42-explore-caching` (linked). See [`tasks/README.md`](tasks/README.md).

## Format

Each task:

```markdown
## <task-id>
- status: backlog
- parent: <optional-related-task-id>
- blocked_by: <optional-task-id>
- goal: One sentence
- done_when: Observable acceptance criteria
- notes: Optional one-liner
```

Detail lives in `dev/tasks/<task-id>/task.md` (and any other files in that folder) when needed.

---

<!-- Add tasks below. Example:

## PROJ-42-example-feature
- status: backlog
- goal: …
- done_when: See `dev/tasks/PROJ-42-example-feature/task.md`.
- notes: …

-->
