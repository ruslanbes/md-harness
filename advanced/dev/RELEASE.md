# Release runbook

Related: [BACKLOG.md](BACKLOG.md), [STATUS.md](STATUS.md), [tasks/README.md](tasks/README.md)

## When to release

Cut a release when:

- One or more backlog items are complete (all `done_when` criteria met).
- [CHANGELOG.md](../CHANGELOG.md) `[Unreleased]` contains a significant work chunk.
- Project tests / build (and CI on the default branch, if any) are green.

Ad-hoc changelog updates without a version tag are fine anytime; this runbook is for **promoting `[Unreleased]` → `[X.Y.Z]`** and cleaning finished task artifacts (backlog rows + `tasks/` folders).

## Pre-release checklist

<!-- Replace with this repo’s real commands. -->

- [ ] Tests pass.
- [ ] Build / package (if any) succeeds.
- [ ] Manual smoke checks for user-facing changes (if applicable).

## Prepare the release

### 1. Clean the backlog

In [BACKLOG.md](BACKLOG.md):

- **Remove** entries whose work is fully captured in the new changelog section.
- Create missing CHANGELOG entries in the `[Unreleased]` section if needed.
- Keep `backlog` / `ready` / `in_progress` / `blocked` items.
- Remove cancelled tasks and their detail folders.
- Do **not** leave stale `done` rows after a release — the changelog is the archive of shipped work.

### 2. Analyze and cleanup task folders

Per [tasks/README.md](tasks/README.md): delete `dev/tasks/<task-id>/` for tasks shipped in this release or cancelled.

Keep the `dev/tasks/` folder, `tasks/README.md`, and `tasks/TEMPLATE/`. Behavior should live in CHANGELOG, ADRs, FAQ, and layer READMEs — not in deleted specs.

#### 2.1 Handling detailed task docs

- Task folders are temporary artifacts. On release we clean them up.
- Read each finished `task.md` (and skim other files in the task folder if they hold decisions).
- Check if any durable docs (`dev/README.md`, FAQ, ADRs, layer READMEs) reference the task folder.
- Extract important architectural decisions and contracts, summaries of diagrams and tables, and user-facing behavior.
- Check if that info is covered where it belongs: process/ground rules in `dev/README.md`; product/architecture in FAQ, ADRs, or layer READMEs.
- If those docs have gaps, move the extracted material there. Create new durable docs if needed; review them before commit.

### 3. Refresh session status

Update [STATUS.md](STATUS.md):

- Set **Current focus** / **Active task** to what’s next.
- Clear or shorten **Session notes** for the released work (one line “Released X.Y.Z” is enough).
- Confirm **Blockers** is accurate.

### 4. Finalize the changelog

Edit [CHANGELOG.md](../CHANGELOG.md):

1. Review `[Unreleased]` — group under **Added** / **Changed** / **Removed** / **Fixed** (Keep a Changelog).
2. Add a new dated section, e.g. `## [0.2.0] - YYYY-MM-DD`.
3. Move items from `[Unreleased]` into that section.
4. Leave `[Unreleased]` empty (or with a placeholder comment) for the next cycle.
5. Rephrase for **readers of the repo** — user-facing behavior, not internal implementation trivia. Link ADRs or FAQ where useful.
6. Do **not** add a “Completed task specs” line under Removed.
7. Do **not** stage changes as part of release *preparation* unless the project’s workflow says otherwise.

## Execute the release

1. Stage the changes.
2. Publish:

```sh
git commit -m "Release X.Y.Z"
git tag -a vX.Y.Z -m "Release X.Y.Z"
git push origin HEAD --tags
```

<!-- Adjust branch name, CI, and deploy verification for this project. -->
