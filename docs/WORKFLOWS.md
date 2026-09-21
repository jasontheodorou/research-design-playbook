# Workflows

## Reader journeys

### The new joiner, first session

Arrives from a link in a welcome message. Has twenty minutes and no context.
Reads the main site start to finish. Leaves able to say how research and design
work at Transform, and what is expected of them.

They should not have to choose a path, filter anything, or decide what to read
first. The front door does that for them.

### The practitioner, looking something up

Knows what they want. Arrives mid-task, often from a search or a colleague's
link. Finds the method or example, takes what they need, leaves.

They should never be made to read a linear narrative to reach a reference.

### Sharing a link

Someone sends a colleague a link to a specific page. It opens on that page.

This is the journey the previous build could not support at all, and the reason
deep-linked routes are a requirement.

## Editorial workflow

Roles, as named:

- **Editor** — creates and edits drafts. Cannot publish.
- **Publisher** — everything an editor can do, and can publish.
- **Admin** — everything a publisher can do, and manages users and roles.

The path:

1. An editor changes text, an image or a video, and saves a draft.
2. They preview the draft as it will appear.
3. A publisher reviews and publishes — or the editor requests that someone does.

**In v1 this is one person.** The roles are built and real, because retrofitting
permissions is worse than building them, but in practice the same person drafts
and publishes. The request-publish notification is deferred until there is a
second person to notify.

## Decision workflow

A decision becomes a record when it is consequential. Consequential means any
of:

- it changes what a user experiences;
- it commits the project to a cost, a dependency or a constraint;
- reversing it later would mean rewriting code that other code depends on.

Choosing a database is consequential. Naming a variable is not. When unsure,
write the record — they are cheap.

The record states the context, the decision, why, **what was rejected**, and the
consequences. A record without the rejected alternative is incomplete.

Records live in `docs/decisions/` as `NNNN-slug.md`, numbered sequentially.
Never renumber. A decision that is later reversed is superseded by a new record
that references it, not edited or deleted.

## Where agents fit

Agents draft, measure, summarise and propose. A human approves anything
consequential, and publication is always a human act.

This is a seam, not a feature. Nothing is automated in Phase 0, and no agents
or tooling are built until repeated work proves they are needed.

Two rules hold whenever an agent is involved:

- **Evidence beats fluency.** A confident proposal that contradicts what a real
  user did loses to the user.
- **Proposals are labelled.** Content or design that came from an agent is
  known to have come from an agent when a human reviews it.

See [`AGENTIC-UCD.md`](AGENTIC-UCD.md).

---

See also: [`CHARTER.md`](CHARTER.md), [`ARCHITECTURE.md`](ARCHITECTURE.md).
