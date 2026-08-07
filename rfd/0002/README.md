---
rfd: "0002"
title: Release management process
authors:
  - Founding team
state: published
discussion: (link to the PR that merged this)
---

# RFD 0002: Release management process

## Problem

Without a defined release rhythm, shipping degenerates into either "release
whenever something is ready" (no predictability, no forcing function for
quality) or death-march launches (everything lands at once, quality and people
suffer). We need a cadence that scales from a two-person team to a large one,
and that works for software releases and physical-product launches alike.

## Proposal

Adopt a **release-train model** adapted from Kubernetes sig-release: a fixed
cadence, named phase gates (freezes), explicit rotating roles, and a single
tracking issue per cycle that serves as checklist, record, and handoff
document.

The full living process is documented in [`releases/README.md`](../../releases/README.md)
and its templates. Summary of what this RFD commits us to:

- **Fixed cadence, flexible scope.** A release ships on its date with
  whatever cleared the freezes. Features that miss catch the next train.
- **Phase gates**: scope freeze → feature/design freeze → code/tooling freeze
  → launch → retrospective. Exceptions to a freeze require an explicit,
  recorded exception request to the release lead.
- **Rotating release lead** with a shadow, so release knowledge never lives
  in one head. Subteam roles (signal/quality, docs, comms) are hats that may
  all sit on one or two people early on.
- **One tracking issue per cycle**, from the template, checkbox-driven, that
  doubles as the retrospective input and the next lead's onboarding document.

## Alternatives considered

- **Continuous deployment only.** Right for the software deploy pipeline, but
  it doesn't answer "what do we announce, when, with docs and support ready?"
  — marketing-visible releases still need a train. The two coexist.
- **Ship-when-ready.** No forcing function; scope grows to fill unlimited
  time.
- **Full Kubernetes ceremony (5 subteam leads + shadows, 15-week cycle).**
  Too heavy now; we adopt the structure (phases, roles, tracking issue) at
  startup scale and grow into the ceremony as the team grows.

## Trade-offs and risks

- Trains create deadline pressure at freezes. Mitigated by making
  scope-cutting the honored move, not the shameful one.
- Physical products have supplier lead times that don't respect neat cycles;
  the product-track adaptation in `releases/README.md` addresses this with
  longer cycles and earlier freezes.

## Implementation / rollout

`releases/README.md`, the tracking-issue template, and the retrospective
template implement this RFD. Running the first full release cycle marks it
`committed`.

## Open questions

- Cycle length (6 weeks proposed for software; per-program for hardware) —
  validate after two cycles and amend `releases/README.md` via PR.
