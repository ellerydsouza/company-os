---
rfd: "0007"
title: Engineering platform and practice (adopting k8s-project-playbook)
authors:
  - Founding team
state: published
discussion: (link to the PR that merged this)
---

# RFD 0007: Engineering platform and practice

## Problem

The company has pre-existing, battle-tested engineering documentation —
[ellerydsouza/k8s-project-playbook](https://github.com/ellerydsouza/k8s-project-playbook)
— covering Go services on a self-hosted Kubernetes platform (Forgejo CI,
ArgoCD GitOps, Kustomize, sealed secrets, Traefik, Cilium). It predates this
operating system and lives outside it. Unadopted, it's tribal knowledge; and
several of its hard-won operational lessons (notably GitOps self-heal
behavior) contradict assumptions in our existing playbooks.

## Proposal

1. **Adopt the external repo as the engineering mechanics reference**, by
   link, not by copy. It is already versioned, public, and self-contained;
   duplicating its 600 lines here would fork it. This repo holds the
   *policy*; that repo holds the *how*.
2. **Extract the durable conventions** — the ones that would survive a
   change of cluster or even language — into
   [`handbook/engineering.md`](../../handbook/engineering.md).
3. **Wrap its new-service bootstrap as a house playbook**
   ([`playbooks/new-service-bootstrap.md`](../../playbooks/new-service-bootstrap.md))
   so the playbook index remains the single place to look up procedures.
4. **Correct the incident-response playbook** for GitOps reality: on a
   selfHeal cluster, hand-applied mitigations (`kubectl set env`, `kubectl
   edit`) are reverted within minutes. Rollback means *revert in git and let
   ArgoCD sync* (or use runtime admin/gRPC toggles, which selfHeal cannot
   revert).

This RFD also constitutes recorded evidence for [RFD 0006](../0006/README.md):
a working software delivery platform and practice already exist, which
weights the software (or hybrid) path.

## Alternatives considered

- **Copy the docs into this repo**: single-repo convenience, but guarantees
  drift between two copies; rejected — cross-link instead (house rule 7).
- **Leave it external and unreferenced**: it remains invisible to the
  operating system, and the incident-playbook contradiction stays latent.
- **Migrate this platform decision itself through a fresh evaluation**
  (managed cloud vs self-hosted): premature — the platform exists and works
  at current scale. A future RFD when scale, team, or customer requirements
  (SLAs, compliance) demand managed infrastructure.

## Trade-offs and risks

- Policy here, mechanics there — two places to look. Mitigated by
  consistent linking and by `handbook/engineering.md` staying thin.
- The external repo is public; anything company-specific (real hostnames,
  topology) must never be added to it. Specifics stay in private
  project-repo CLAUDE.md files, per its own placeholder convention.

## Implementation / rollout

`handbook/engineering.md`, `playbooks/new-service-bootstrap.md`, the
incident-response correction, and index updates. Marked `committed` when the
first product service is bootstrapped through the playbook.

## Open questions

- Self-hosted vs managed cloud for *customer-facing production* (uptime,
  on-call, data residency) — deliberately out of scope here; becomes an RFD
  when RFD 0006 resolves and the first production SLA is contemplated.
