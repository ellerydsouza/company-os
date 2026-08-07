# Playbook: Incident response

**Trigger:** Anything customer-impacting or data-threatening: outage, severe
degradation, data loss/corruption risk, security event, or — for a physical
product — a safety issue or field-failure pattern.
**Owner:** Engineering lead
**Last verified:** 2026-08-06 (initial draft — verify against first real incident)

## Before you start

- Access required: production dashboards, status page admin, alerting tool,
  customer-comms channel.
- Severity guide: **SEV1** = customers can't use the product / data or safety
  at risk. **SEV2** = major feature broken, workaround exists. **SEV3** =
  minor, fix in normal course.

## Steps

1. **Declare it.** Post in `#incidents`: severity, one-line symptom, and "I am
   incident commander" (IC) — whoever declares is IC until handed off.
   Under-declaring is worse than over-declaring; downgrade later is free.
2. **Stabilize before you diagnose.** Prefer the reversible mitigations:
   rollback last deploy, disable the feature flag, fail over, rate-limit.
   Root cause hunting comes after customers stop hurting.
   **On the GitOps cluster, rollback means revert in git** (revert the
   tag-bump/manifest commit and let ArgoCD sync) — hand-applied fixes
   (`kubectl set env`, `kubectl edit`) are reverted by selfHeal within
   minutes. Runtime admin/gRPC toggles are the only reliable in-the-moment
   levers; see [handbook/engineering.md](../handbook/engineering.md).
3. **Communicate at declare + every 30 min** (SEV1) or hourly (SEV2):
   status page / customer channel update — what's affected, what we're doing,
   next update time. Never promise a fix time; promise the next update.
4. **Log as you go** in the incident thread: timestamps, actions, findings.
   You will not remember the order of events afterward.
5. **Hand off if it runs long.** IC and responders swap out at ~3 hours;
   tired people make incidents longer.
6. **Close the incident** when impact has ceased and the mitigation is
   stable: announce internally, final status-page update, thank responders.
7. **Schedule the post-incident review** within 3 business days for
   SEV1/SEV2. Blameless; use the retrospective format
   ([template](../releases/templates/retrospective.md), adapted). SEV1
   reviews that reveal systemic causes should produce an RFD, not just a fix.

*(Hardware/safety variant: step 2 = stop-ship decision first — halt outbound
units before diagnosing; step 3 includes regulatory notification check.)*

## Escalation

- SEV1: wake the engineering lead and CEO immediately, any hour.
- Security or safety events: engineering lead + CEO + legal counsel before
  any external statement beyond the status page.
- Stop following the script when: law enforcement, regulators, or press are
  involved — escalate to CEO and improvise nothing in writing.

## Done when

- Impact ceased, mitigation stable, closure announced, review scheduled with
  an owner.
- [ ] If any step was wrong, missing, or confusing: open a PR fixing this
  playbook before you close the incident.
