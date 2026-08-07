---
rfd: "0001"
title: The RFD process
authors:
  - Founding team
state: published
discussion: (link to the PR that merged this)
---

# RFD 0001: The RFD process

## Problem

Startups make many consequential decisions quickly, and by default those
decisions live in chat threads, meetings, and founders' heads. That fails in
predictable ways: context is lost, decisions get re-litigated, new hires can't
learn *why* things are the way they are, and quieter voices don't get heard in
real-time discussion.

Writing ideas down allows them to be rigorously formulated (even while
nascent), candidly discussed, and transparently shared. We want a lightweight,
uniform mechanism for that — one that covers not just technical architecture
but company processes, product direction, and organizational decisions.

## Proposal

We adopt **Requests for Discussion (RFDs)**: numbered documents, living in
this repository, moving through a defined state machine, discussed on pull
requests.

### When to write an RFD

Write an RFD for anything where the decision or the reasoning deserves a
record, including:

- Product architecture and design decisions (software **or** physical product
  — industrial design directions, component/vendor selection, manufacturing
  approach)
- APIs, interfaces, and anything with compatibility promises
- Company processes (hiring, compensation philosophy, release cadence)
- Significant tooling or vendor choices
- Go-to-market or pricing changes with lasting consequences
- Changes to any existing RFD-governed process — including this one

Rule of thumb: **if it would take a meeting to decide, or you'd want to know
"why" in a year, write an RFD.** Trivially reversible choices don't need one.

Anyone at the company may write an RFD. Authorship is not restricted by role
or seniority.

### States

| State | Meaning |
|---|---|
| `prediscussion` | Author is actively iterating; not ready for broad feedback |
| `ideation` | A scoped idea parked for others to pick up or co-develop |
| `discussion` | Open PR; actively soliciting feedback |
| `published` | Merged after convergence; the decision stands |
| `committed` | Fully implemented; describes reality, not intent |
| `abandoned` | Not pursued — merged anyway as a record of the dead end |

Transitions are ordinary commits/PRs updating the `state:` metadata.
Discussion may continue on the original PR even after merge, to keep the
conversation in one findable place.

### Mechanics

1. Reserve the next sequential number; branch `rfd/NNNN`; create
   `rfd/NNNN/README.md` from the template; push early to claim the number.
2. Iterate locally until ready, then open a PR and set `state: discussion`.
3. Discussion window: **3–5 business days** by default. Extend for large or
   contentious RFDs; shorten only with explicit agreement of those affected.
4. The **author decides** which feedback to incorporate. Convergence means
   objections were heard and addressed or explicitly acknowledged — not
   unanimity. If discussion deadlocks, the relevant decision owner (CEO for
   company-wide matters until otherwise delegated) breaks the tie in the PR.
5. Merge, set `state: published`, and update the index in `rfd/README.md`.
6. When implementation lands, flip to `committed` and update any handbook
   pages or playbooks the RFD affects. **RFDs are history; the handbook is
   the present.** Never rewrite a published RFD to match changed reality —
   write a superseding RFD and cross-link both.

### Discussion norms

Feedback is about the idea, never the person. Be direct and be kind — both.
Ask questions before objecting; steelman before you strawman. Silence during
the window is consent.

## Alternatives considered

- **Decision meetings + minutes.** Faster in the moment, but excludes async
  and quiet contributors, and minutes capture conclusions without reasoning.
- **ADRs (Architecture Decision Records).** Good, but scoped to technical
  architecture. RFDs deliberately cover company process and product decisions
  too; one mechanism beats two.
- **Wiki/Notion docs.** No state machine, no review gate, no durable
  numbering; documents rot without a lifecycle.

## Trade-offs and risks

- Writing is slower than deciding in a hallway. Accepted: the cost is paid
  once, the context is reused forever.
- Risk of process theater — RFDs for trivia. Mitigated by the rule of thumb
  above; when in doubt, a short RFD is fine, a skipped one for a big decision
  is not.
- Risk of stale states (things published but never marked committed). Sweep
  states during release retrospectives.

## Implementation / rollout

- This repository structure, the template in `rfd/templates/template.md`, and
  the index in `rfd/README.md` constitute the implementation.
- Later, as volume grows (per Oxide's experience): a bot to enforce naming and
  metadata, short URLs, and a rendered site. Not needed on day one.

## Open questions

- At what team size do we need tooling (bot, rendered site) rather than
  convention? Revisit around 10 people or 50 RFDs, whichever comes first.
