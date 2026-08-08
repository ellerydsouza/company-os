---
rfd: "0009"
title: Mission, principles, and values
authors:
  - (unclaimed — founder to develop)
state: ideation
discussion: —
---

# RFD 0009: Mission, principles, and values

> **State: ideation.** Scopes the decision; does not make it. Modeled on
> [Oxide RFD 2](https://rfd.shared.oxide.computer/rfd/0002), whose
> architecture we propose to reuse with our own content.

## Problem

The handbook has a values page pending with no architecture behind it.
Without written mission/principles/values, hard calls get made ad hoc — and
several downstream processes (hiring evaluation, partnership selection, an
LLM policy) work best when they can resolve tensions by pointing at an
explicit ordering of what matters.

## Proposal: the three-layer architecture

1. **Mission** — why the company exists, one memorable sentence.
2. **Principles** — the non-negotiable constraints (Oxide's: integrity,
   honesty, decency). Never traded off against anything, including each
   other. Deliberately few.
3. **Values** — the competing priorities (candor, curiosity, rigor,
   urgency, thriftiness, …). Listed **alphabetically** so no hierarchy is
   implied — values genuinely tension against each other, and naming that
   tension is the point.

The distinction does real work: principles answer "may we do this at all?";
values answer "which good thing wins here?". Downstream documents
(hiring, partnerships, LLM use) should cite specific values when justifying
trade-offs.

## Decisions this RFD must make

- The mission sentence (waits naturally on [RFD 0006](../0006/README.md)).
- The principle set — Oxide's three are a strong default; what, if
  anything, differs for us?
- The value list — genuinely ours, not copied; each value needs one
  sentence of what it means *here*.
- Internalization mechanics: Oxide requires memorization. Our equivalent?
  (Minimum: values cited by name in RFD trade-off sections.)

## Exit criteria for ideation

Founder claims authorship, drafts the three layers, moves to `discussion`.
On publish: `handbook/values.md` created; hiring and future partnership
docs updated to reference it.
