# Playbook: New service bootstrap

**Trigger:** A decision to build a new deployable service (for anything
customer-facing or architecturally significant, that decision itself gets an
RFD first).
**Owner:** Engineering lead
**Last verified:** 2026-08-06 (wraps the external playbook; verify on first
use for the startup's product)

This playbook is a thin wrapper: the full mechanics live in
[NEW_PROJECT_PLAYBOOK.md](https://github.com/ellerydsouza/k8s-project-playbook/blob/main/docs/NEW_PROJECT_PLAYBOOK.md)
(per [RFD 0007](../rfd/0007/README.md), mechanics stay in the reference repo).

## Before you start

- Read [handbook/engineering.md](../handbook/engineering.md) — the
  conventions the external playbook implements.
- Access: Forgejo (repo creation in the org), cluster kubeconfig, registry.
- Have decided: service name, single-module vs workspace (§0 of the external
  playbook), and which node tier it runs on.

## Steps

1. **Work through the external playbook §0–§11 in order** — repo shape, Go
   module/versioning, vendoring, lifecycle skeleton, config, telemetry,
   Dockerfile, Kustomize, CI/GitOps/secrets/networking, testing gate, gRPC.
2. **Complete its §12 bootstrap checklist verbatim** — every box, including
   the project `CLAUDE.md` with the port table. The checklist is the
   contract; "mostly done" services are the ones that page you later.
3. **Validate before first deploy:** `kubectl kustomize ... | kubectl apply
   --dry-run=server -f -` passes; CI green end-to-end (build → test → lint
   → images → tag-bump); ArgoCD app syncs and the pod goes Ready.
4. **Register the service in this repo:** add its ports/URLs to the project
   CLAUDE.md, and if it introduces a new external dependency or paid
   service, add the [vendor-register](../finance/vendor-register.md) row in
   the same sitting.
5. **Confirm health + metrics are actually scraped** (not just exposed) —
   check Prometheus targets, and that a NetworkPolicy hasn't silently
   blocked probes (external playbook §9 / infra §8 carve-out).

## Escalation

- Platform-level surprises (storage class behavior, ArgoCD sync oddities,
  NetworkPolicy mysteries): check
  [CLUSTER_INFRASTRUCTURE.md](https://github.com/ellerydsouza/k8s-project-playbook/blob/main/docs/CLUSTER_INFRASTRUCTURE.md)
  gotchas first — most of them are already documented there as paid-for
  mistakes.
- Gaps or errors found in the *external* playbook: PR that repo, then update
  `Last verified:` here.

## Done when

- All §12 checklist boxes ticked, CI green, ArgoCD synced, pod Ready,
  metrics scraped, project CLAUDE.md current.
- [ ] If any step was wrong, missing, or confusing: open a PR fixing this
  playbook (or the external repo) before you close the task.
