# Working agreement — research-design-playbook

Terse responses. No trailing summaries. Match scope to what was asked.

## Project

A learning product for service designers and interaction designers at
Transform UK. Currently Phase 0: documents only, no application code.

Read `docs/CHARTER.md` before proposing anything about scope. Read
`docs/ARCHITECTURE.md` before proposing anything about the stack.

## Clean-room boundary

A previous build of this material exists elsewhere on this machine as a React
and Vite application. It is evidence, not implementation.

- **You may read** its decision records, lessons, content and structure to
  understand what the product is and what has already been learned.
- **You may not copy** its source code, styling, component architecture or CMS
  implementation.

If you are unsure which side of the line something falls on, describe the
intent rather than the mechanism.

## Settled decisions

These are constraints, not suggestions. Do not reopen them without being
asked.

1. Clean-room rebuild. The original repository is evidence, not implementation.
2. Next.js and Payload in one application.
3. Real deep-linked routes. Every page is addressable.
4. Server rendering by default.
5. Text, images and video are all editable.
6. Design system deferred behind a token seam. No brand system is chosen.
7. Real user evidence remains authoritative.
8. Humans approve consequential design decisions.

## Decisions

Write decisions to `docs/decisions/NNNN-slug.md` using the next free number.
Never renumber an existing decision. Record the rejected alternative, not just
the decision taken.

A decision is consequential enough to need a record if reversing it later
would mean rewriting code that other code depends on, or if it commits the
project to a cost, a dependency or a constraint.

## Method

`docs/AGENTIC-UCD.md` describes how this project is meant to work. It is a
hypothesis drawn from a previous build, not proven practice. Revise it from
what actually happens here, and record the revision.

## No speculative automation

Do not create custom agents, skills or hooks. Do not add tooling. When the
same work has been done by hand enough times that the pattern is obvious,
propose automating it then — and say what evidence prompted the proposal.

## Ownership

Currently a personal prototype under the `jasontheodorou` GitHub account.
Commits are authored as `Jason Alfredos <jay.alfredos.labs@gmail.com>`. It may
later transfer to Transform UK.

Until ownership, access and hosting are formally resolved, do not let
client-confidential, personal or commercially sensitive content into this
repository. This applies to git history, not only the working tree — assume
anything committed is permanent.

## Deploy identity

The commit author must have access to the Vercel team that owns this project.
Otherwise the push succeeds and the deploy fails silently, leaving production
on the previous commit with no visible error.

Check after committing: `git log -1 --format='%an <%ae>'`

## Portability

This repository must work on someone else's machine. Do not add dependencies
on directory conventions, installed tooling, scheduled jobs, port registries or
global configuration outside this repository.
