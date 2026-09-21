# 0001 — Clean-room rebuild

- **Status:** accepted
- **Date:** 2026-09-21

## Context

A version of this material already exists as a React and Vite single-page
application. It is deployed and in use.

It also carries defects its own decision journal records: no deep links into
any page, an access gate implemented as a hardcoded password compiled into the
client bundle which provides no meaningful security and contradicts the
environment-variable behaviour its documentation describes, a stub route left
rendering nothing, and a pattern library that drifted from the product it was
meant to demonstrate. A CMS was scaffolded and never installed.

Two rebuild attempts have already been started. Neither produced application
code. The risk being managed is not technical — it is starting a fourth attempt
that stalls like the previous two.

## Decision

Rebuild clean-room. **The original repository is evidence, not implementation.**

What may be taken from it:

- decision records and recorded lessons;
- what the content says, as evidence of what to write;
- the information architecture, as evidence of what worked and what did not;
- documented problems and their causes.

What may not be taken from it:

- source code;
- styling;
- component architecture;
- CMS implementation.

Content is re-authored rather than migrated.

## Why

The defects above are not incidental. They follow from decisions taken early —
a single-page application with no server, a client-side gate, a content model
held in code — and they cannot be fixed by porting the code that expresses
them.

Re-authoring roughly eight thousand words is a smaller cost than carrying
forward assumptions nobody can now reconstruct.

A partial boundary is more expensive to hold than a clean one. "Copy this but
not that" requires a judgement at every file. "Read it, do not copy it" requires
one rule.

## Rejected alternatives

- **Incremental refactor of the existing application.** Rejected: the defects
  follow from the architecture, so the refactor becomes a rewrite with extra
  steps and no clean point to stop.
- **Fork and strip.** Rejected: leaves the original's structure in place by
  default, which is exactly what needs re-deciding. The boundary would be
  negotiated file by file.
- **Migrate content and assets wholesale.** Rejected: the content is small
  enough to re-author, and the photography has no consent or licence record, so
  it could not move regardless.

## Consequences

- No source code, styling, component architecture or CMS implementation is
  copied.
- Decisions and lessons are inherited deliberately, and this is the main thing
  of value being carried forward.
- Content is written new. Nothing reaches parity with the previous build, and
  parity is explicitly not a goal.
- The original repository is left untouched. Nothing is deleted, moved or
  archived.
- Photography does not move without evidenced consent, which does not currently
  exist.
- Anyone working here needs the boundary stated plainly, because the temptation
  to reach for a working implementation is constant. It is in `CLAUDE.md`.
