# Development

How we run this project: ground rules, setup, release process, and current work tracking.

## Local setup

<!-- Fill in: prerequisites, install, how to run locally, how to run tests / build. -->

```sh
# TODO: install and run commands for this repo
```

## Ground rules

- Track work here in `dev/` — flat backlog, status, optional task folders under `tasks/<task-id>/`.
- Task IDs: `[external-tracker-id-]kebab-slug` (local slug alone until a ticket exists).
- Work one task at a time.
- Before implementing, check for missing decisions; lock them in the task doc (or an ADR) instead of guessing.
- Use [Mermaid](https://mermaid.js.org/) diagrams for architecture documentation.
- When cutting a version or cleaning shipped work, follow [`RELEASE.md`](RELEASE.md).

<!-- Add project-specific policies below (compatibility, code style, layering rules, etc.). -->

## What's in this folder

| Doc | Role | Lifetime |
|-----|------|----------|
| [`README.md`](README.md) (this file) | Setup, ground rules, doc index | Stable |
| [`RELEASE.md`](RELEASE.md) | Release runbook | Stable |
| [`BACKLOG.md`](BACKLOG.md) | Flat task index | Living — cleaned on release |
| [`STATUS.md`](STATUS.md) | Current focus / blockers / session notes | Living — refreshed each session |
| [`tasks/`](tasks/) | Optional folder per task (`task.md` + free-form supporting files) | Temporary — deleted when the task ships or is cancelled |

## Reference docs

| Doc | Role |
|-----|------|
| [`docs/adr/`](../docs/adr/) | Architecture Decision Records |
| [`docs/faq/`](../docs/faq/) | Stable concepts and how-tos |
| [`CHANGELOG.md`](../CHANGELOG.md) | Shipped user-facing history |

<!-- Link concrete ADRs and FAQ pages here as they appear. -->
