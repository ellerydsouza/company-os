# Engineering practice

The durable engineering conventions — the ones that hold regardless of which
cluster, or even which language, we're on. Adopted via
[RFD 0007](../rfd/0007/README.md). Platform mechanics (CI pipeline, GitOps,
storage, secrets, ingress, networking) live in the
[k8s-project-playbook](https://github.com/ellerydsouza/k8s-project-playbook)
reference repo — link there, don't restate here.

## Source of truth

1. **GitOps: git is the source of truth for deployed state.** Change git and
   let the sync tool apply it; never hand-fix the cluster and walk away —
   self-heal reverts manual drift within minutes. Read-only `kubectl` is
   always fine; mutations that matter go through git.
2. **Every service repo carries a current `CLAUDE.md`**: layout, build/test
   commands, port table, in-cluster URLs, non-obvious decisions — updated in
   the same commit as the change it documents.
3. **Company-specific values (hostnames, topology, credentials) never enter
   public repos.** The public playbook uses placeholders by design; the real
   values live in the private project repos.

## Quality gates

4. **Reproducible, offline builds.** Dependencies are vendored and
   committed; CI must not reach the network to build.
5. **Coverage gates ratchet up, never down.** Per-package thresholds; adding
   code to a gated package means adding tests. Lowering a threshold requires
   an RFD-grade justification.
6. **Lint locally before pushing** — the lint job gates image builds, so a
   lint failure means nothing deploys.
7. **Verify, don't assume**: server-side dry-run for manifests, empirical
   allow/deny tests for network policies, and confirm the workload stays
   Ready after a change lands.

## Operational defaults

8. **Every long-running service** exposes liveness + readiness health
   endpoints, structured logs (`slog`; mutating/operator events at WARN),
   and metrics — via the shared lifecycle/config/telemetry packages.
9. **Containers are hardened by default**: non-root, read-only root
   filesystem, no privilege escalation, tini as PID 1, explicit image tags
   (never `:latest` under GitOps management).
10. **Versioned artifacts**: every binary knows and logs its version + git
    hash; image tags encode version-date-sha.
11. **Confirm before outward-facing or hard-to-reverse actions** — push,
    live deploy, data deletion. (The repo-level rule; it echoes
    [decision-making](decision-making.md).)

## Where the mechanics live

| Topic | Reference |
|---|---|
| Bootstrap a new service | [new-service-bootstrap playbook](../playbooks/new-service-bootstrap.md) → [NEW_PROJECT_PLAYBOOK](https://github.com/ellerydsouza/k8s-project-playbook/blob/main/docs/NEW_PROJECT_PLAYBOOK.md) |
| Platform: CI, GitOps, storage, secrets, ingress, NetworkPolicy, observability | [CLUSTER_INFRASTRUCTURE](https://github.com/ellerydsouza/k8s-project-playbook/blob/main/docs/CLUSTER_INFRASTRUCTURE.md) |
| Production rollback during an incident | [incident-response playbook](../playbooks/incident-response.md) |
