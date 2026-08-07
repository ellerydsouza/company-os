---
rfd: "0003"
title: Operating cadence and first domain processes
authors:
  - Founding team
state: published
discussion: (link to the PR that merged this)
---

# RFD 0003: Operating cadence and first domain processes

## Problem

RFDs 0001–0002 established the meta-processes: how we decide and how we ship.
But nothing yet invokes them on a schedule, and the first domain processes a
company needs — watching its money and growing its team — are undefined. Left
unwritten, these default to founder memory: financial review happens when
someone gets nervous, and hiring is improvised per candidate, which is both
slow and a fairness problem.

## Proposal

Adopt three things:

1. **An operating cadence** ([`handbook/operating-cadence.md`](../../handbook/operating-cadence.md))
   — the single calendar of recurring rituals (weekly, monthly, quarterly,
   annual), each with an owner, inputs, and outputs. Any recurring meeting or
   review that is not on this page does not exist; any process we adopt later
   must register its rituals here.
2. **A hiring playbook** ([`playbooks/hiring.md`](../../playbooks/hiring.md))
   — a structured loop (role definition → scorecard → screen → loop →
   debrief → references → offer) so every candidate for a role is evaluated
   against the same bar, and hiring quality survives being busy.
3. **A monthly financial review**
   ([`playbooks/monthly-financial-review.md`](../../playbooks/monthly-financial-review.md))
   — a fixed monthly ritual producing a one-page report (cash, burn, runway,
   actual vs plan) archived in `finance/reviews/`. Runway below 12 months
   triggers an explicit decision, not a feeling.

## Alternatives considered

- **Ad hoc rhythm** ("we'll meet when there's something to discuss"): every
  ritual decays to zero under delivery pressure — the calendar is the forcing
  function.
- **Adopting a full framework (EOS, Scaling Up) wholesale**: heavyweight, and
  much of it duplicates the RFD/release machinery we already have. We take
  the cadence idea and leave the rest.
- **Deferring hiring process until the first hire is imminent**: offers get
  made under time pressure; the process must exist *before* the pressure.

## Trade-offs and risks

- Cadence pages rot when rituals are skipped silently. Mitigation: the
  quarterly operating-system retro reviews skipped rituals by count.
- A hiring playbook this early is partly speculative; it will be revised
  after the first real loop (the runner-updates-the-playbook rule applies).

## Implementation / rollout

The three documents above, plus a `finance/reviews/` archive directory,
implement this RFD. Marked `committed` after one full month of the cadence
has actually run.

## Open questions

- Compensation philosophy (bands, equity approach) deliberately deferred to
  its own RFD — required before the first offer goes out.
- Board/investor reporting cadence deferred until there is a board.
