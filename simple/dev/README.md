# Development

How we run this project: ground rules, setup, release process, and current work tracking.

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
- When cutting a version or cleaning shipped work, follow [`RELEASE.md`](RELEASE.md).

<!-- Add project-specific policies below (compatibility, code style, layering rules, etc.). -->

## What's in this folder

| Doc | Role | Lifetime |
|-----|------|----------|
| [`README.md`](README.md) (this file) | Setup, ground rules, doc index | Durable |
| [`RELEASE.md`](RELEASE.md) | Release runbook | Durable |
| [`BACKLOG.md`](BACKLOG.md) | Flat task index | Living — cleaned on release |
| [`STATUS.md`](STATUS.md) | Current focus / blockers / session notes | Living — refreshed each session |
| [`tasks/`](tasks/) | Optional detail for a backlog item | Temporary — deleted when the task ships or is cancelled |

## Reference docs

| Doc | Role |
|-----|------|
| [`docs/adr/`](../docs/adr/) | Architecture Decision Records |
| [`CHANGELOG.md`](../CHANGELOG.md) | Shipped user-facing history |

<!-- Link concrete ADRs and other project docs here as they appear. -->
