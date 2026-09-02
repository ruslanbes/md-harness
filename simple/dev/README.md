# Development

How we run this project: ground rules, setup, cleanup, release, and current work tracking.

## Local setup

<!-- Fill in: prerequisites, install, how to run locally, how to run tests / build. -->

```sh
# Specific install and run commands for this repo
```

## Ground rules

- Track work here in `dev/` — flat backlog, status, optional task detail files under `tasks/`.
- Work one task at a time.
- Before implementing, check for missing decisions; lock them in the task doc (or an ADR) instead of guessing.
- Use [Mermaid](https://mermaid.js.org/) diagrams for architecture documentation.
- When cleaning finished or cancelled work, follow [`CLEANUP.md`](CLEANUP.md). When cutting a version, follow [`RELEASE.md`](RELEASE.md).

<!-- Add project-specific policies below (compatibility, code style, layering rules, etc.). -->

## What's in this folder

| Doc | Role | Lifetime |
|-----|------|----------|
| [`README.md`](README.md) (this file) | Setup, ground rules, doc index | Durable |
| [`CLEANUP.md`](CLEANUP.md) | Promote durable content; remove finished tasks | Durable |
| [`RELEASE.md`](RELEASE.md) | Version changelog, bump version sources, tag | Durable |
| [`BACKLOG.md`](BACKLOG.md) | Flat task index | Living — cleaned via CLEANUP.md |
| [`STATUS.md`](STATUS.md) | Current focus / blockers / session notes | Living — refreshed each session |
| [`tasks/`](tasks/) | Optional detail for a backlog item | Temporary — deleted when the task ships or is cancelled |

## Reference docs

| Doc | Role |
|-----|------|
| [`docs/adr/`](../docs/adr/) | Architecture Decision Records |
| [`CHANGELOG.md`](../CHANGELOG.md) | Shipped user-facing history |

<!-- Link concrete ADRs and other project docs here as they appear. -->
