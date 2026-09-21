# Charter

## What this is

A learning product that helps service designers and interaction designers at
Transform UK do good research and design work — and keep doing it.

## Who it is for

Transform service designers and interaction designers. New joiners first: the
person in their first month who needs to understand how the work is done here.
Established practitioners second, as a reference they return to.

It is not for clients. It is not for the public.

## The two surfaces

The previous build had two pathways that behaved like siblings. They should
not be. The two surfaces are different in kind:

**The main site.** Immersive, linear, read start to finish. It makes the case
for how research and design work at Transform. A reader arrives, reads, and
leaves with a point of view. This is the front door.

**The depth surface.** Opt-in, non-linear, looked up rather than read. Methods,
practice detail, worked examples. A reader arrives knowing what they want,
finds it, and leaves. Nobody is expected to read it through.

Treating these as one thing is what made the previous build hard to navigate.

## First release: Katsura

The first release is named **Katsura**. Its scope is fixed. It is not a target
to grow into — it is the whole of the first release, and anything not listed
here is a later release.

### Reader-facing product

A home page, five main-journey pages and three depth pages. Nine pages total.

**Main journey**, read in order:

1. Welcome
2. Our purpose
3. Why good design matters
4. How we work
5. Participation

**Depth pages**, looked up as needed:

1. Journey mapping
2. Service blueprinting
3. Co-design

### Platform capability

- Every page has a permanent, deep-linkable URL.
- Payload administrator authentication.
- Editors can change text, images and video.
- Draft, preview and publish workflow.
- Neutral token-based visual foundation.
- Responsive layouts.
- Keyboard accessibility.
- Reduced-motion behaviour.
- End-to-end deployment.

### Explicitly excluded from Katsura

- Reader accounts.
- Progress tracking.
- Role or account filtering.
- Personalisation.
- A complete method library.
- Client-confidential content.

These are excluded from this release. Some may never be built; see the
out-of-scope list below, which is permanent rather than deferred.

Reasoning, rejected alternatives, and the evidence that would justify
expanding this scope are recorded in
[`decisions/0003-katsura-release-scope.md`](decisions/0003-katsura-release-scope.md).

## Out of scope

Stated plainly so it does not creep back in:

- **Content parity with the previous build.** Content is re-authored, not
  migrated. The old corpus is evidence of what to write.
- **Client-confidential material.** Nothing that could not be shown to someone
  outside the account.
- **A public surface.** This is internal. A public version may follow; it is
  not v1.
- **Personalisation.** No per-user progress tracking, no recommendations, no
  role-based filtering in v1. These were built before and earned their keep
  less than they cost.

## What is not being rebuilt, and why

- **The pattern library.** It drifted from the product it demonstrated, which
  destroyed the guarantee that made it useful.
- **The access gate as it stands.** The previous gate is a hardcoded password
  compiled into the client bundle. It offers no meaningful security, and it
  contradicts the environment-variable behaviour the old repository documents.
  Whether this project needs real authentication is an open question — but it
  will not ship something that describes itself as protection while providing
  none.
- **Role and account filtering.** Complexity that served a small audience.

## The asset rule

No photograph of an identifiable person is used without evidenced consent.

The previous build holds 34 workshop photographs showing identifiable people.
No licence, attribution or consent record exists anywhere in that repository.
Until that evidence exists, those images do not move.

This applies to any new photography too. Consent is recorded at the point of
capture, with the asset.

## Ownership and what may enter the repository

Currently a personal prototype, owned under the `jasontheodorou` GitHub
account, with commits authored as
`Jason Alfredos <jay.alfredos.labs@gmail.com>`. It may later transfer to
Transform UK.

Until ownership, access and hosting are formally resolved, **no
client-confidential, personal or commercially sensitive content may enter the
repository.**

This is stricter than the out-of-scope list above. That concerns what the
product shows; this concerns what the repository holds at all, history
included.

## How we will know it is any good

- A new joiner reads the main site and can describe how design works here.
- A practitioner finds what they came for in the depth surface without asking
  anyone.
- Someone shares a link to a specific page, and it opens on that page.
- Content is changed by someone who cannot write code.

---

See also: [`ARCHITECTURE.md`](ARCHITECTURE.md), [`WORKFLOWS.md`](WORKFLOWS.md),
[`AGENTIC-UCD.md`](AGENTIC-UCD.md).
