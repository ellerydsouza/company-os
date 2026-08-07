---
rfd: "0004"
title: Security baseline, offboarding, and vendor register
authors:
  - Founding team
state: published
discussion: (link to the PR that merged this)
---

# RFD 0004: Security baseline, offboarding, and vendor register

## Problem

Security practice, access lifecycle, and vendor sprawl are the three areas
that are nearly free to systematize at day one and expensive to retrofit:
customers will eventually send security questionnaires, a departed person's
lingering access is a classic breach vector, and untracked auto-renewing
contracts silently eat runway. None of these currently have a written process.

## Proposal

Adopt three artifacts:

1. **A security baseline** ([`handbook/security.md`](../../handbook/security.md))
   — the minimum rules everyone follows (password manager, 2FA, access
   granting via a recorded request, tested backups, laptop hygiene), written
   to double as the raw material for future customer security questionnaires.
2. **An offboarding playbook** ([`playbooks/offboarding.md`](../../playbooks/offboarding.md))
   — the mirror of onboarding, run the same day a departure is decided:
   access revoked from a maintained inventory, knowledge handed off, equipment
   and comms handled with dignity.
3. **A vendor/contract register** ([`finance/vendor-register.md`](../../finance/vendor-register.md))
   — one table of every vendor: cost, renewal date, notice period, owner, and
   what it would take to leave. Reviewed at the annual vendor/insurance
   ritual already on the [operating cadence](../../handbook/operating-cadence.md),
   and by the monthly financial review when explaining spend deviations.

The security baseline's access-inventory rule is what makes the offboarding
playbook runnable — they are adopted together deliberately.

## Alternatives considered

- **Wait for a customer questionnaire / compliance requirement (SOC 2)** to
  force the issue: retrofitting practice under deal pressure produces
  checkbox security. Writing the baseline now costs an afternoon.
- **Track vendors in the bookkeeping system only**: books capture what was
  paid, not notice periods, owners, or exit costs — the register exists for
  the renewal-date and lock-in questions.

## Trade-offs and risks

- A baseline nobody audits becomes fiction. Mitigation: the quarterly
  operating-system retro spot-checks two rules; the annual ritual reviews all.
- The access inventory is the fragile piece — it only works if granting
  access and recording it are the same act. The baseline makes that the rule.

## Implementation / rollout

The three documents implement this RFD. Marked `committed` once the access
inventory and vendor register are populated with reality (not templates).

## Open questions

- When to pursue SOC 2 / ISO 27001 — deferred until a customer requires it;
  the baseline is written so that day is a gap analysis, not a rewrite.
