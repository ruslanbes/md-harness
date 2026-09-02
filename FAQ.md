# FAQ

## Why not use Jira / GitHub Issues / etc. instead?

You can use Jira instead, or another specialized task tracker. There are pros and cons of each approach.

Use external tracker if:

- You want a clear separation of process tracking from the code (e.g. there are different permissions)
- You already track the project there (legacy tickets)
- You have an integration that creates tickets from your users (e.g. via ServiceNow -> Jira)
- Etc.

Use markdown-based tracker if:

- You are a single developer.
- You are the product architect who wants to track ideas for the product.
- You want to store all project-related knowledge in one place.
- You want agents to quickly start working on your project without pulling extra information from external sources.

You can also use the `advanced` template as an addition to Jira.

So, the main benefit of the markdown-based tracker is speed. The main sacrifice is multi-user support and separation of concerns.

## How does it compare with similar tools?

These all live in the “help humans and coding agents run work from the repo” space. They are not the same kind of thing.


|                      | **md-harness**                                                                 | **[Backlog.md](https://github.com/MrLesk/Backlog.md)**         | **[GitHub Spec Kit](https://github.com/github/spec-kit)**   | **[Beads](https://github.com/gastownhall/beads)**                 |
| -------------------- | ------------------------------------------------------------------------------ | -------------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------------- |
| **What it is**       | File templates + process conventions you copy into a repo                      | Task manager product (CLI, board, optional MCP)                | Spec-driven workflow toolkit (CLI + agent slash commands)   | Agent-oriented issue tracker (`bd`) with a graph DB               |
| **Storage**          | Plain markdown (and whatever else you put next to tasks)                       | Plain markdown tasks, usually edited via the tool              | Markdown specs / plans / task lists under a Spec Kit layout | Dolt-backed DB (not freeform markdown TODOs)                      |
| **Runtime**          | None — editors and agents read files                                           | Install and run `backlog`                                      | Install `specify`; wire slash commands into an agent        | Install and run `bd`                                              |
| **Main focus**       | Ongoing process: backlog, session status, ADRs, changelog, cleanup + release | Managing and visualizing tasks                                 | Building a feature: specify → plan → tasks → implement      | Long-horizon agent work: deps, ready queue, multi-agent claiming  |
| **Docs / decisions** | First-class (`docs/adr`, promote on cleanup)                              | Secondary to task tracking                                     | Specs are the center for a change; not a full ADR/FAQ kit   | Project memory via the tool (`remember` / `prime`), not ADRs      |
| **Best fit**         | Solo monorepo that wants a light, editable harness with no install             | Want a real markdown task board + CLI without inventing format | Want a structured SDD loop for larger features              | Want structured issues for agents more than human-edited markdown |


**TL;DR:** md-harness is a layout and cleanup/release habit, not a product. Backlog.md is the closest neighbor if you mainly want task files. Spec Kit is heavier and feature-shaped. Beads solves a similar problem with the opposite storage bet (DB/graph instead of freeform markdown).

## I already have a repository with a working project, can I install md-harness into it?

Yes, but you need to carefully adapt it without overwriting your files. Chances are, you already have top-level `CHANGELOG.md`, `AGENTS.md` and `docs` folder.

Try using the following prompt with your agent:

```
Install simple md-harness from https://github.com/ruslanbes/md-harness into this existing repo.
Merge, do not overwrite:
- If a file already exists, leave its content. Append or add a pointer only when needed; say what you skipped.
- AGENTS.md: if missing, copy it. If it exists, add a line to follow dev/README.md.
- CHANGELOG.md: keep the existing file. If it has no [Unreleased] section, add one. Do not create a second changelog.
- docs/: add adr/ next to whatever is already there. Do not replace docs/.
- .cursor/rules/workflow.mdc: add alongside other rules; do not replace the rules folder.
- dev/: if the folder does not exist, copy it. If it does, pick another name (ask me first) and update every harness path to match.
Then list what you added vs what you merged.
```


## What should I add to gitignore?

Normally nothing. You might add `.cursor/` if you prefer to keep its configuration local. If you don't use Cursor, you can delete that dir. 