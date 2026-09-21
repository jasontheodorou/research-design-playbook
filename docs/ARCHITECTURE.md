# Architecture

**Proposed, not built.** Nothing in this document exists yet. It records the
shape the application is intended to take and the decisions already settled.

## One application

Next.js App Router and Payload run as a single application. Payload mounts
inside the Next app.

The previous plan called for a second, separate deployment for the CMS, wired
back to the main site by a rewrite. That seam disappears. One codebase, one
deployment, one place to reason about.

Recorded in [`decisions/0002-nextjs-payload.md`](decisions/0002-nextjs-payload.md).

### What this means for content access

Because Payload runs inside the same application, the site reads content
through Payload's local API — an in-process call, not a network request to a
separate service.

**Do not design around a network-fetch architecture.** There is no HTTP hop
between the site and the CMS in the default path, and therefore no inherent
network timeout, retry or transport-failure case to handle there. Assuming
otherwise imports complexity this architecture does not have.

## Server rendering by default

Pages render on the server. Client components are used only where interaction
demands them, and the reason is worth stating in the component.

This is what makes the rest of the architecture possible: content read directly
at render time, real URLs, and no loading states for content that could have
been rendered.

## Real deep-linked routes

Every page is individually addressable.

In the previous build the URL never changed as a reader moved through the
material. Nothing could be linked to, bookmarked, or shared at the point that
mattered. Screenshot and test scripts had to click through the whole sequence
each time.

This is the single clearest defect being designed out. It is a requirement, not
an enhancement.

## Editable text, images and video

All three are first-class editable fields. The previous plan allowed text
editing only and fixed the imagery in v1.

This raises the architectural floor and should not be waved through:

- **Images** need storage, upload handling, and generated sizes.
- **Video** needs storage, bandwidth, and a decision about whether it is
  transcoded or uploaded ready to play.

Media storage is therefore an architectural concern from the start, not an
afterthought. It is an open decision below.

## Token seam

One module exports neutral design tokens: colour, type, space, shape, motion.
Every component reads tokens. **A raw hex value in a component is a defect.**

No brand system is chosen or wired. This is deliberate, and it is the reason
the seam exists: the choice can be made once, later, without rework.

Two systems on this machine both claim ownership of Transform's colour and type.
They derive different values from the same brand and are not composable. That
choice is not Phase 0's to make.

Until it is made, tokens hold neutral placeholder values. The seam is real; the
values are not.

## Open decisions

None of these are guessed here. Each gets a decision record when it is decided.

| Decision | Why it is open |
|---|---|
| **Caching and content-failure behaviour** | Depends on how content is actually read and how often it changes. What is cached, for how long, how a change invalidates it, and what a page does when content cannot be loaded, are all unsettled. Do not assume a fail-open-to-last-known-good model; it was carried over from a different architecture and does not automatically apply. |
| **Component library** | Decides whether existing brand work ports at all. Needs a spike against server rendering, since component libraries vary widely in how much they force to the client. |
| **Database host** | Several options are viable at this scale. Decide when provisioning. |
| **Media storage** | Follows from the video decision. Local, object storage, or a managed media service. |
| **Reader access** | Payload administrator authentication is settled and in scope for Katsura; this row concerns readers only. The previous access gate is a hardcoded password compiled into the client bundle. It provides no meaningful security, and it contradicts the environment-variable behaviour that repository's documentation describes. This application has a server, so real authentication is now possible. Whether it is needed depends on whether anything sensitive ever sits behind it. |

## Not carried over

The previous build's tooling is tied to its stack and does not port:

- Its single-page-application rewrite rule would conflict with Next's router.
- Its build-time URL substitution is unnecessary; Next has native metadata.
- Its draft-mode checks use build-tool-specific globals that do not exist here.

---

See also: [`CHARTER.md`](CHARTER.md), [`WORKFLOWS.md`](WORKFLOWS.md),
[`decisions/0001-clean-room-rebuild.md`](decisions/0001-clean-room-rebuild.md).
