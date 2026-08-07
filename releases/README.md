# Release Management

How we ship on a cadence. Adopted via [RFD 0002](../rfd/0002/README.md);
modeled on [Kubernetes sig-release](https://github.com/kubernetes/sig-release)
practice (see e.g. their [release-cycle tracking
issues](https://github.com/kubernetes/sig-release/issues/2934)), scaled down
to startup size.

## Principles

1. **The date is fixed; the scope is not.** A release ships on schedule with
   whatever cleared the freezes. Cutting scope is the honored move.
2. **Freezes are real.** After a freeze, exceptions require an explicit
   request to the release lead, recorded in the tracking issue with the risk
   and the justification. "It's basically done" is not a justification.
3. **One tracking issue per cycle.** Copied from the template at cycle start,
   checked off as the cycle runs. It is simultaneously the checklist, the
   audit trail, the retrospective input, and the next lead's training manual.
4. **Roles rotate; shadows learn.** Every role has a named owner and, once
   headcount allows, a shadow who leads next cycle. Release knowledge must
   never live in exactly one head.
5. **Every cycle ends in a retrospective**, and retrospective actions land as
   PRs to these documents or as new RFDs — otherwise the retro was theater.

## Roles

At small scale several hats sit on one person — but name each hat explicitly
in the tracking issue anyway, so nothing is silently unowned.

| Role | Owns |
|---|---|
| **Release lead** | The calendar, freeze decisions, exception calls, the tracking issue, go/no-go |
| **Signal / quality** | Test & CI health (or QA/validation builds for hardware); the "is it actually green?" answer |
| **Docs** | User-facing docs, changelogs, internal runbook updates matching the release |
| **Comms** | Announcement, customer notifications, support-team briefing, launch coordination |
| **Branch manager** *(software)* | Cutting the release branch, cherry-pick approvals after code freeze, building candidates |

## The cycle (software track — default 6 weeks)

| Week | Phase | Gate |
|---|---|---|
| 0 | **Planning** — pick roles, copy the tracking issue, collect candidate scope | **Scope freeze**: the cycle's intended contents are listed |
| 1–3 | **Build** — normal development; weekly scope check against the tracking issue | |
| 4 | **Stabilize** — release branch cut; only fixes land on it | **Feature freeze** |
| 5 | **Harden** — release candidates, docs finalized, comms drafted | **Code freeze**: fixes for release-blockers only, via exception |
| 6 | **Ship** — go/no-go, release, announce, monitor | **Launch** |
| +1 | **Close** — retrospective, actions filed, tracking issue closed, handoff to next lead | |

Continuous deployment of the service continues throughout — this cycle governs
*marketing-visible, compatibility-relevant* releases (the versioned artifact,
the announcement, the docs), not every deploy.

## The cycle (product/hardware track)

Same skeleton, different physics: cycles are per-program rather than
per-6-weeks, freezes come much earlier relative to launch, and some gates are
irreversible (tooling, certification, mass production). Mapping:

| Software gate | Hardware equivalent |
|---|---|
| Scope freeze | Product requirements locked |
| Feature freeze | **Design freeze** (EVT exit — no new functionality) |
| Code freeze | **Tooling/DVT freeze** (changes now cost tooling money and weeks) |
| Release candidate | PVT units |
| Launch | Mass production go + shipping + announcement |

Extra standing checklist items for hardware cycles: supplier lead-time
tracking from week 0, certification (FCC/CE/UL) started before design freeze,
packaging and fulfillment on the same tracking issue as the product itself.

## Artifacts

- [`templates/release-tracking-issue.md`](templates/release-tracking-issue.md)
  — copy at cycle start (into the issue tracker or as
  `releases/cycles/YYYY-MM-name.md`)
- [`templates/retrospective.md`](templates/retrospective.md) — run within one
  week of launch
- `releases/cycles/` — the archive of past cycles; the institutional memory
