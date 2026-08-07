---
rfd: "0006"
title: Business direction — software, physical product, or both
authors:
  - (unclaimed — founder to develop)
state: ideation
discussion: —
---

# RFD 0006: Business direction — software, physical product, or both

> **State: ideation.** The operating system in this repo was deliberately
> built to support either path. This RFD is where the actual direction gets
> decided and recorded — it is the single highest-leverage undecided question
> in the company.

## Problem

"Could be software, could be a product-based business" is the current honest
state. That ambiguity is fine for building process scaffolding; it is not
fine for hiring, fundraising, or the first release cycle, all of which need
to know what business this is. The cost structures, capital needs, iteration
speeds, and risk profiles of the two paths differ enough that most downstream
decisions hang on this one.

## Decisions this RFD must make

1. **What is the product**, in one paragraph, and who is the first customer
   (a person you can name or describe precisely, not a market)?
2. **Which path** — pure software, physical product with companion software,
   or hardware-enabled service? What evidence supports it (customer
   conversations, prototypes, domain advantage)?
3. **What the choice implies**, made explicit:
   - *Software:* 6-week release train activates as-is; capital needs are
     mostly salary; iterate-in-production is available.
   - *Physical product:* the hardware track in [`releases/README.md`](../../releases/README.md)
     activates (EVT/DVT/PVT gates); the supplier section of the
     [vendor register](../../finance/vendor-register.md) becomes live; the
     [financial review](../../playbooks/monthly-financial-review.md) must
     model inventory and tooling cash-lumps; mistakes ship in atoms and
     recall in dollars.
   - *Both:* sequencing question — which comes first and what does the other
     wait for?
4. **What would change our mind** — the observable signals that would trigger
   a superseding RFD rather than a slow drift.

## Evidence on file

- [RFD 0007](../0007/README.md): a working software delivery platform and
  engineering practice (Go on self-hosted Kubernetes, GitOps, CI with
  quality gates) already exist and are documented. This weights the software
  or hybrid path — the software side has infrastructure momentum; a pure
  hardware path would strand it.

## Inputs to gather before drafting

- 10–20 problem-discovery conversations with candidate customers, written up.
- A rough cost model per path (runway impact via the financial-review
  template's lumpy-costs section).
- An honest inventory of founder advantage: what do you know/have that others
  don't, and which path does it compound in?

## Exit criteria for ideation

Founder claims authorship, answers the four decisions with evidence, moves to
`discussion`. On publish: the first release cycle gets scheduled on the
chosen track, and the unused track's machinery stays documented but dormant.
