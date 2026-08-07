---
rfd: "0008"
title: Engineering onboarding — structural proactivity and the golden path
authors:
  - Founding team
state: discussion
discussion: (open a PR when moving to a shared remote; discussing in-place until then)
---

# RFD 0008: Engineering onboarding — structural proactivity and the golden path

## Problem

Two known-bad patterns for developer onboarding, both experienced firsthand:

1. **Docs-heavy front-loading** — a week of reading with nothing to attach
   it to. Knowledge pushed before the person knows which questions they
   have doesn't stick.
2. **Synthetic mentoring-project ladders** (ment1/ment2/ment3-style) —
   throwaway projects nobody depends on: perfunctory reviews, no production
   feedback, weeks of being economically invisible, and skills that don't
   transfer because the hard parts (real pipelines, other people's code,
   legacy constraints) are exactly what's omitted.

The deeper failure mode underneath both: **they rely on new-hire
proactivity.** The mentee is expected to request knowledge dumps and ask
about the things they don't know — but new hires have the least context
(unknown unknowns), the lowest comfort, and the strongest social incentive
not to look ignorant. An onboarding that only works for the boldest
personality is broken by design.

## Proposal

**Design principle: proactivity is structural, not personal. The system
initiates; the new hire never has to.**

### 1. Mentor-led walkthrough series (attacks unknown unknowns)

Scheduled on the calendar *before day 1*, mentor-driven, ~45 minutes each
across the first two weeks:

- Architecture tour — the system as it actually is, including the warts
- Deploy pipeline + platform — CI → GitOps → cluster, live
- Ops war stories — the gotchas already paid for (the
  [infrastructure doc's](https://github.com/ellerydsouza/k8s-project-playbook/blob/main/docs/CLUSTER_INFRASTRUCTURE.md)
  caveat sections, narrated)
- Product and customer context — who buys this and why

The agenda is "what I wish I'd known" — content only the mentor can supply,
delivered by default rather than on request.

### 2. The buddy contract (inverts the accountability)

- Buddy-initiated 15-minute check-in, daily, weeks 1–2 — calendared in
  advance so the mentee never weighs "is this worth bothering them."
- Buddy is the new hire's **code reviewer** for weeks 1–2 — the
  relationship has real shared stakes, not tour-guide content.
- **The silence red flag:** few questions by day 3 is the *buddy's* problem
  to fix (more pairing, more outreach), never evidence the hire is fine.
  Question volume is a health metric of the onboarding, not of the person.

### 3. The question log (makes asking a deliverable)

The mentee keeps a running log: every question, every answer, dated. Rules:

- An empty log at end of week 1 triggers buddy action — shyness becomes
  visible instead of silent.
- Every logged answer not found in existing docs becomes a docs PR (this
  feeds the existing onboarding exit rule: everyone fixes at least one doc).
- The log is reviewed at the week-2 manager check-in as *input about the
  docs*, explicitly not as an assessment of the hire.

### 4. Day 1–2: the golden-path deploy (replaces "read the docs first")

Pair — not solo — through the
[new-service-bootstrap playbook](../../playbooks/new-service-bootstrap.md):
a trivial service, taken through the full real pipeline to Ready and
scraped, then torn down (teardown is also curriculum). Everything around
the toy service is real: the CI, the review, the cluster, the gotchas.
**Record time-to-first-deploy per hire** — it is the platform's primary
onboarding metric, and every slow onboarding is a usability test failure
of the platform, not of the person.

### 5. The responsibility ladder (replaces the synthetic project ladder)

Progression through graduated *real* stakes, each rung legible:

1. First trivial real PR through the full pipeline (day 1–3)
2. First real backlog ticket (week 1–2)
3. First incident shadow (as schedule allows)
4. First release-role shadow — plugging into the shadow structure already
   defined in [releases](../../releases/README.md)
5. Running a release role

This keeps the one virtue of ment1/2/3 (visible progression) while fixing
everything else: real reviews, real feedback, real value from week one.

### 6. Docs are pulled, not pushed

The required reading list stays as-is in
[onboarding](../../handbook/onboarding.md) (short, foundational). Everything
else is linked just-in-time from the task that needs it. No doc-reading
phases.

### On IDPs (Backstage et al.)

Adopt the concepts, defer the product: scaffolder → automate the bootstrap
checklist as a template/script when friction warrants; catalog → per-repo
CLAUDE.md + an index page past ~3 services; TechDocs → docs-in-repo
(already). Revisit a real IDP at roughly 15–20 engineers — running
Backstage below that scale costs more than it saves.

## Alternatives considered

- **Docs-first onboarding**: no hooks to hang knowledge on; rejected.
- **Synthetic project ladder**: no stakes, invisible work, poor transfer;
  rejected — see Problem.
- **"Hire proactive people" / rely on mentee initiative**: selects for
  confidence over competence and fails exactly the people onboarding
  exists to serve; this is the motivating failure.

## Trade-offs and risks

- Mentor/buddy time is a real cost (~30–60 min/day for two weeks). Accepted
  deliberately: it's bounded, and the alternative cost (a slow, quiet ramp)
  is larger and hidden.
- Daily check-ins can feel like surveillance if framed wrong — the framing
  is "the buddy owes you time," never "we're checking on you."

## Implementation / rollout

On publish: extract `handbook/onboarding-engineering.md` from §1–§6, amend
the buddy section of `handbook/onboarding.md` with the contract in §2, and
add the walkthrough-series calendar seed to the pre-day-1 checklist.
`committed` after the first real engineering hire completes it.

## Open questions

- Should the golden-path exercise stay synthetic-but-real (bootstrap +
  teardown) or be an actual small backlog item? Current lean: synthetic for
  the deploy exercise, real for the first PR — decide before first hire.
- Record the walkthrough sessions for reuse, or keep them live-only?
  (Recordings scale but rot; live sessions renew with each telling.)
