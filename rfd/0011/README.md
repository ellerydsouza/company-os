---
rfd: "0011"
title: LLM and AI-agent use policy
authors:
  - (unclaimed — founder to develop)
state: ideation
discussion: —
---

# RFD 0011: LLM and AI-agent use policy

> **State: ideation.** Informed by
> [Oxide RFD 576](https://rfd.shared.oxide.computer/rfd/0576), but our
> starting point differs sharply: Oxide *discourages* LLM-generated prose
> and code in critical systems; our engineering playbooks are explicitly
> written for Claude Code instances to execute, and much of this very
> operating system was agent-drafted. We need a policy that fits an
> agent-forward practice honestly rather than importing one written for an
> agent-skeptical one.

## Problem

Agent-assisted work is already our default mode, with no written rules.
The risks of leaving it implicit: unreviewed generated artifacts shipping
with nobody meaningfully accountable; sensitive values (per the
[security baseline](../../handbook/security.md) and two-repo scheme in
[engineering](../../handbook/engineering.md)) leaking into prompts or
public repos; and — as the team grows — divergent individual practices
with no shared social contract about disclosure and trust.

## The principle to build on (transfers directly from Oxide)

**Responsibility is never outsourced.** The human owns every artifact
regardless of what automation produced it. "The agent wrote it" is never
an account of a defect — the committer's name is on the commit.

## Decisions this RFD must make

- **Review standard**: what self-review is mandatory before agent-produced
  code/docs go to peer review or merge? (Oxide: self-review is essential;
  our volume makes the *depth* the real question.)
- **Provenance/disclosure**: we already trailer AI-authored commits
  (`Co-Authored-By`). Where else is disclosure owed — RFDs? customer-facing
  text? incident comms?
- **Data boundaries**: what may enter prompts/contexts of cloud-hosted
  models — customer data? real cluster values? (The internal/public
  playbook split already encodes one answer; generalize it.)
- **Where agents may act autonomously** vs where a human must drive:
  production changes, external communications, anything under the
  [incident playbook](../../playbooks/incident-response.md)?
- **Anti-patterns to codify** (Oxide's list holds): no mandates to use
  LLMs, no shaming for using or not using them, no anthropomorphizing
  agents as accountable parties.

## Exit criteria for ideation

Founder claims and drafts; on publish, becomes `handbook/ai-use.md`, and
the engineering handbook + project CLAUDE.md conventions reference it.
