# Task folders

Optional deep-dive workspace for a backlog item. One **folder** per task ID:

```
dev/tasks/<task-id>/
  task.md          ← main file (required)
  …                ← any other files/folders this task needs
```

Only `task.md` is required. Supporting material (notes, samples, analysis, assets, drafts, …) may live next to it; layout is free and can differ from task to task.

Use a folder when the task needs planning, analysis, championing, or coordination beyond what fits in `BACKLOG.md`. Keep `BACKLOG.md` as the index (status, goal, done_when).

## Task IDs

Format: `[external-tracker-id-]kebab-slug`

| Form | Example | When |
|------|---------|------|
| Local only | `explore-caching` | Temporary idea; not (yet) in Jira/Linear/etc. |
| Tracker-linked | `PROJ-42-explore-caching` | Work has an external ticket |

When a local task matures and gets a ticket, rename the folder and update the backlog heading / `task.md` ID to include the tracker id (keep the slug stable when possible).

## Creating a task folder

```sh
mkdir -p dev/tasks/<task-id>
cp dev/tasks/TEMPLATE/task.md dev/tasks/<task-id>/task.md
```

Edit `task.md`. Add other files in the same folder as needed. Do not leave a folder literally named `TEMPLATE` as a real task.

## Lifetime

Task folders are temporary: delete the whole `dev/tasks/<task-id>/` directory on release when the task ships or is cancelled (see [`../RELEASE.md`](../RELEASE.md)). This README and `TEMPLATE/` stay.
