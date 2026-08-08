---
rfd: "0012"
title: Record every meeting
authors:
  - (unclaimed — founder to develop)
state: ideation
discussion: —
---

# RFD 0012: Record every meeting

> **State: ideation.** Modeled on
> [Oxide RFD 537](https://rfd.shared.oxide.computer/rfd/0537). Small
> policy, cheap to adopt, best decided before the first hire so it's the
> water everyone swims in rather than a change imposed later.

## Problem

Our [communication norms](../../handbook/communication.md) make written and
async the default, but synchronous conversation still happens and is pure
loss today: decisions made aloud must be re-written (or evaporate), absent
people can't catch up without a retelling, and onboarding loses its richest
raw material. Recording turns synchronous time into a durable artifact at
near-zero cost.

## Proposal (to develop)

- **Default-on recording + transcription for all scheduled meetings**,
  attached to the calendar event (discoverability solved by the calendar).
- **Ad-hoc sessions too** when they turn substantive — debugging sessions
  especially (it is never too late to hit record).
- **Standing exceptions**: personnel/hiring discussions, most 1:1s,
  external parties who decline (customers asked with consent, link
  offered).
- **Watching a recording carries no status penalty** vs live attendance —
  this is the transparency point, and it reinforces async-first rather
  than competing with it.
- Recordings feed the existing promotion rule: decisions still get written
  into RFDs/handbook — a recording is a record, not a substitute for the
  written decision.

## Decisions this RFD must make

- Tooling and storage (calendar-attached cloud recordings vs self-hosted —
  ties into the [vendor register](../../finance/vendor-register.md) and
  [security baseline](../../handbook/security.md) data rules).
- Retention period, and who may access what.
- Whether the [onboarding walkthrough series](../0008/README.md) sessions
  are recorded (RFD 0008's open question — resolve it here).

## Exit criteria for ideation

Claimed, tooling chosen, moved to discussion; on publish, a paragraph in
`handbook/communication.md` and the exceptions list becomes policy.
