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

## How does it compare with other tools?

These all live in the “help humans and coding agents run work from the repo” space. They are not the same kind of thing.


|                      | **md-harness**                                                                 | **[Backlog.md](https://github.com/MrLesk/Backlog.md)**         | **[GitHub Spec Kit](https://github.com/github/spec-kit)**   | **[Beads](https://github.com/gastownhall/beads)**                 |
| -------------------- | ------------------------------------------------------------------------------ | -------------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------------- |
| **What it is**       | File templates + process conventions you copy into a repo                      | Task manager product (CLI, board, optional MCP)                | Spec-driven workflow toolkit (CLI + agent slash commands)   | Agent-oriented issue tracker (`bd`) with a graph DB               |
| **Storage**          | Plain markdown (and whatever else you put next to tasks)                       | Plain markdown tasks, usually edited via the tool              | Markdown specs / plans / task lists under a Spec Kit layout | Dolt-backed DB (not freeform markdown TODOs)                      |
| **Runtime**          | None — editors and agents read files                                           | Install and run `backlog`                                      | Install `specify`; wire slash commands into an agent        | Install and run `bd`                                              |
| **Main focus**       | Ongoing process: backlog, session status, ADRs/FAQ, changelog, release cleanup | Managing and visualizing tasks                                 | Building a feature: specify → plan → tasks → implement      | Long-horizon agent work: deps, ready queue, multi-agent claiming  |
| **Docs / decisions** | First-class (`docs/adr`, FAQ, promote on release)                              | Secondary to task tracking                                     | Specs are the center for a change; not a full ADR/FAQ kit   | Project memory via the tool (`remember` / `prime`), not ADRs      |
| **Best fit**         | Solo monorepo that wants a light, editable harness with no install             | Want a real markdown task board + CLI without inventing format | Want a structured SDD loop for larger features              | Want structured issues for agents more than human-edited markdown |


**TL;DR:** md-harness is a layout and release habit, not a product. Backlog.md is the closest neighbor if you mainly want task files. Spec Kit is heavier and feature-shaped. Beads solves a similar problem with the opposite storage bet (DB/graph instead of freeform markdown).