# Agentic UCD

A way of doing user-centred design when some of the work is done by agents.

## Status: hypothesis

**This is not proven practice.** It is drawn from lessons recorded during a
previous build of this material — a body of evidence, but a small one, from a
single project.

It is written down first so it can be tested, contradicted and revised. Treat
every principle below as a claim awaiting evidence, not as doctrine.

The revision log at the end starts empty. If it is still empty when the
product ships, something has gone wrong: either nobody checked, or nobody was
honest about what they found.

## Principles

### 1. Real user evidence is authoritative

Agent output is a proposal, however fluent. It never outranks what a user
actually did.

When a well-argued agent recommendation and a scrappy observation from a real
session disagree, the observation wins. Fluency is not evidence, and an agent's
confidence carries no information about whether it is right.

*Enforced by:* nothing yet. Aspirational. Needs a habit of naming the evidence
behind a design claim, and noticing when there is none.

### 2. Humans approve consequential design decisions

Agents draft, measure, summarise and propose. A human decides.

Consequential means: it changes what a user experiences, it commits the project
to a cost or dependency, or reversing it would mean rewriting code that other
code depends on.

*Enforced by:* the decision record. A consequential change without an ADR is a
process failure.

### 3. Evidence, not assertion

A screenshot is evidence. A description of a screenshot is not.

An agent reporting that a page looks right is reporting its expectation, not
its observation. The gap between those two is where defects live.

*Enforced by:* nothing yet. Needs verification tooling, which Phase 0 does not
build. Aspirational until it exists.

### 4. Under ambiguity, build less

When the brief is unclear, ship the bare thing and ask. Do not ship a hedge.

In the previous build, an ambiguous request for a page produced an invented
placeholder full of filler content. It was rejected outright, and the route was
reduced to nothing. The lesson recorded at the time: ambiguity is a reason to
build less, not a reason to build a guess.

Agents are especially prone to this. Asked for something underspecified, they
produce something plausible rather than stopping.

*Enforced by:* the working agreement in `CLAUDE.md`.

### 5. Record the rejected alternative

A decision without its discarded option is not a decision record. It is an
announcement.

The value of a decision log is telling a future reader what was considered and
set aside, so they do not spend a day rediscovering why.

*Enforced by:* the ADR format. Both existing records name what was rejected.

### 6. Failures are kept

Attempts that did not work are not deleted. They are written down with the same
care as the ones that did.

The highest-value records are the failures, because they are the ones nobody
else can reconstruct from the finished product.

*Enforced by:* convention only. Needs somewhere obvious to put them, which does
not exist yet.

### 7. Documented claims must be verifiable

Do not write down a behaviour the code does not have.

The previous build's README described an access gate driven by an environment
variable. No file in the application read that variable. The real gate was a
hardcoded password. The documentation had sat there long enough to read as
established fact, which made it worse than no documentation at all.

Before trusting a claim in prose, check it against the code.

*Enforced by:* nothing yet. Aspirational.

### 8. Measure accessibility, never assert it

Contrast is measured, per element, against the colour actually behind it.

A colour can pass as a background and fail as a foreground mark on itself.
Both cases occurred in the previous build. Neither was caught by eye.

*Enforced by:* nothing yet. Needs tooling. Aspirational.

## What this is not

It is not a claim that agents do user-centred design. It is a description of
how to keep design user-centred when agents are doing some of the work.

The failure mode it guards against is a build that is fast, coherent,
well-documented and wrong — because every input came from a model and nothing
came from a user.

## Honest assessment

Five of the eight principles have no enforcement mechanism. They are
intentions.

Intentions do not survive a deadline. The measure of whether this method is
real will be how many of those five have something behind them by the time v1
ships — and whether the ones that do not get honestly downgraded rather than
quietly kept.

## Revision log

Revisions go here, with the date and what prompted them. A principle that
survives contact with the build unchanged should say so. A principle that turns
out to be wrong should be struck through, not deleted.

*(empty)*

---

See also: [`CHARTER.md`](CHARTER.md), [`WORKFLOWS.md`](WORKFLOWS.md).
