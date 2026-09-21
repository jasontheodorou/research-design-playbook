# 0002 — Next.js and Payload in one application

- **Status:** accepted
- **Date:** 2026-09-21

## Context

The previous build is a React and Vite single-page application with no server.
A CMS was scaffolded separately and never installed; the plan at the time was to
deploy it as a second application and wire it back to the site with a rewrite.

Two requirements make the old shape unworkable. Every page must be individually
addressable, and content must be editable by someone who cannot write code —
including images and video, not only text.

## Decision

Next.js App Router and Payload, in **one application**, with server rendering by
default.

The site reads content through Payload's local API in-process. There is no HTTP
hop between the site and the CMS in the default path.

## Why

- **Deep links need real routes.** A single-page application can fake them; a
  server does not have to.
- **Server rendering needs a server.** Content read at render time removes a
  whole class of loading states and client-side fetching.
- **One application removes the two-deployment seam.** No rewrite between
  projects, no second thing to provision, no cross-service authentication, one
  place to reason about.
- **Payload mounts inside Next natively.** The integration is the supported
  path, not something being forced.

## Rejected alternatives

- **Keep Vite, add a separate CMS deployment.** The original plan. Rejected: two
  deployments, a rewrite seam, cross-service auth, and it still leaves the site
  without a server, so deep links and server rendering remain out of reach.
- **Static site generator with content in git.** Rejected: content must be
  editable by non-developers. A pull request is not an editorial workflow, and
  it rules out image and video upload entirely.
- **A different headless CMS with Next.** Rejected: viable, but a separate
  service reintroduces the network hop and another vendor. Payload running
  in-process is simpler, and the previous build had already selected it, so the
  choice carries some prior thinking even though none of its code does.

## Consequences

- A new stack to learn. The previous build's tooling is tied to Vite and does
  not port.
- **A database becomes a real requirement**, with the hosting and cost that
  implies. Host is an open decision.
- **Media storage becomes a real requirement**, because images and video are
  editable. Open decision.
- Server rendering constrains the component library choice: libraries that force
  most components to the client would undercut the reason for choosing this
  architecture.
- Because the CMS is in-process, **do not design around network-fetch failure
  modes** in the default content path. Caching and content-failure behaviour are
  an open decision, recorded in `../ARCHITECTURE.md`, and must be decided from
  how content is actually read here rather than carried over from the previous
  architecture.
- One deployment, one build, one place where a failure surfaces.
