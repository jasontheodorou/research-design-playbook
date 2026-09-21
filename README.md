# Research and Design Playbook

A learning product for service designers and interaction designers at Transform UK.

## Current state

**Phase 0. Documents only.** There is no application here yet — no code, no
dependencies, no build. This repository currently holds the brief: what is
being built, who it is for, how it will be judged, and which decisions are
already settled.

Do not mistake intent for progress. Nothing in this repository runs.

## How to read this

Read in this order:

1. [`docs/CHARTER.md`](docs/CHARTER.md) — what this is, who for, and what is out of scope.
2. [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md) — the proposed shape of the application.
3. [`docs/WORKFLOWS.md`](docs/WORKFLOWS.md) — how readers use it, and how content gets published.
4. [`docs/AGENTIC-UCD.md`](docs/AGENTIC-UCD.md) — the working method, stated as a hypothesis.
5. [`docs/decisions/`](docs/decisions) — the decision record.

## Background

A previous version of this material exists as a React and Vite single-page
application. It is read-only evidence for this rebuild. Its decisions and
recorded lessons carry forward. Its source code, styling, component
architecture and CMS implementation do not.

See [`docs/decisions/0001-clean-room-rebuild.md`](docs/decisions/0001-clean-room-rebuild.md).

## Ownership

This is currently a **personal prototype**, owned under the `jasontheodorou`
GitHub account. Commits are authored as
`Jason Alfredos <jay.alfredos.labs@gmail.com>`.

It may later transfer to Transform UK.

Until ownership, access and hosting are formally resolved, **no
client-confidential, personal or commercially sensitive content may enter this
repository** — including its history.

## Deploy constraint

This project is intended for Vercel. The commit author must have access to the
Vercel team that owns the project.

If they do not, **the push to GitHub succeeds and the deploy fails silently.**
Production stays on the previous commit and nothing surfaces an error. Check
the author after committing, not before:

```
git log -1 --format='%an <%ae>'
```

## Contributing

Decisions go in `docs/decisions/` as `NNNN-slug.md`, using the next free
number. Never renumber an existing decision.

See [`CLAUDE.md`](CLAUDE.md) for the working agreement.
