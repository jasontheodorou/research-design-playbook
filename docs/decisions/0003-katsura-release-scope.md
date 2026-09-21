# 0003 — Katsura release scope

- **Status:** accepted
- **Date:** 2026-09-21

## Context

The charter previously defined v1 as "the smallest number of pages that is
genuinely worth a designer's time" and left the count open. That is not a
scope; it is an intention to decide later.

This material has been started three times and abandoned twice before any
application code existed. The recurring failure is not technical. It is that
"how much" stays negotiable, so the work never reaches an end state anyone can
point at and call finished.

The first release is therefore named and fixed. **Katsura.**

## Decision

Katsura is nine reader-facing pages — a home page, five main-journey pages and
three depth pages — plus the platform capability needed to run them properly:
permanent deep-linkable URLs, Payload administrator authentication, editable
text, images and video, a draft/preview/publish workflow, a neutral
token-based visual foundation, responsive layouts, keyboard accessibility,
reduced-motion behaviour, and end-to-end deployment.

The full list is in [`../CHARTER.md`](../CHARTER.md).

Excluded: reader accounts, progress tracking, role or account filtering,
personalisation, a complete method library, client-confidential content.

## Why this is the smallest honest end-to-end release

Honest means every layer is real. Nothing is stubbed, faked or deferred to
make a demo hold together.

A smaller release would have to fake something. Drop the CMS and content is not
really editable. Drop the publish workflow and editing is not really safe. Drop
deployment and nothing is really shipped. Each of those omissions would leave
a version that demonstrates well and proves nothing, which is the failure mode
of the previous attempts.

A larger release would not prove anything more. The tenth page exercises the
same routing, the same content model, the same editorial path and the same
deployment as the ninth. Additional pages add content cost and schedule risk
while testing nothing new.

Katsura is the point where every layer is exercised once and no layer is
exercised twice for its own sake.

It also has to be genuinely useful, not merely complete. Nine pages is enough
that a new joiner reading it gets real value, which matters because the release
is only validated by someone actually using it.

## Why five main pages and three depth pages

**Five main pages.** The previous build's linear deck ran to twelve pages, was
consolidated to eight, and its recorded content still amounts to roughly 680
words across those eight — thin pages stretched over too many screens. Five
pages carrying the same argument gives each one enough substance to be worth
turning to, and holds the whole journey inside a single sitting. The five named
sections are the load-bearing ones: what this is, why we exist, why the work
matters, how we do it, and how you take part. Cutting any of them leaves a gap
a new joiner would notice.

**Three depth pages.** The depth surface has to prove three separate things:
that a page works, that a set of pages works as a set, and that the surface is
navigable when the reader arrives cold. One page proves the first only. Two
prove the second weakly. Three is the minimum that demonstrates all three and
establishes a pattern an author can follow without further design work.

Journey mapping, service blueprinting and co-design were chosen because they
are distinct in shape — an artefact-producing method, a systems-analysis
method, and a participatory method. Three variations on the same shape would
have produced a template that broke on the fourth page.

**Nine pages total** is also small enough to re-author from scratch, which the
clean-room decision requires.

## Rejected alternatives

- **Main journey only, no depth pages.** Rejected: leaves the entire second
  surface untested. The charter claims the two surfaces are different in kind;
  building only one leaves that claim unverified and the harder half of the
  information architecture undesigned.
- **One depth page as a proof of concept.** Rejected: a single page proves a
  page renders. It does not surface the navigation, listing or cross-linking
  problems that only appear once a set exists — which is exactly where the
  previous build's structure failed.
- **Eight main pages, matching the previous build.** Rejected: that structure
  was already the result of consolidating twelve, and its pages remained thin.
  Inheriting the count would inherit the problem.
- **Ship without the CMS, using content in code.** Rejected: "editable by
  someone who cannot write code" is a defining requirement. Deferring it would
  repeat the previous build, which scaffolded a CMS and never installed it.
- **A complete method library.** Rejected: unbounded content work in front of
  a release with no shipped product behind it. This is how the previous
  attempts stalled.
- **Leaving the scope open and deciding as we go.** Rejected explicitly. It has
  been tried, and it produced two abandoned rebuilds.

## What evidence would justify expanding the scope

Expansion is earned with evidence from real use, not from confidence that more
would be better. Any of the following would justify a proposal:

- **A new joiner reads the main journey and reports a gap** — something they
  needed to understand and could not find. That names a sixth page.
- **Practitioners repeatedly look for a method that is not there.** Repeatedly
  means more than once, from more than one person. That names the next depth
  page.
- **An editor changes content without help, successfully.** This validates the
  editorial path and is the precondition for adding content volume at all. If
  it fails, the answer is to fix the workflow, not to add pages.
- **Someone shares a deep link and the recipient lands correctly.** Validates
  the routing claim that justifies the whole architecture.
- **Readers navigate the depth surface without asking where things are.** If
  they cannot at three pages, adding more will make it worse, and the surface
  needs redesigning first.

Absent that evidence, the answer to "should we add more" is no.

## Consequences

- Katsura is a fixed scope, not a milestone to grow. Additions go to a later
  release with their own record.
- **Payload administrator authentication is in scope; reader authentication is
  not.** These are different things. Editors log in; readers do not have
  accounts. How reader access is controlled remains open in
  [`../ARCHITECTURE.md`](../ARCHITECTURE.md).
- Nine pages of content must be written. This is the largest non-engineering
  cost in the release and the one most likely to be underestimated.
- Editable video is in scope, so media storage must be resolved before content
  work begins rather than alongside it.
- Keyboard accessibility and reduced-motion behaviour are release criteria, not
  polish. A release failing either is not finished.
- The release is validated by real use. Deployed but unused is not done.
