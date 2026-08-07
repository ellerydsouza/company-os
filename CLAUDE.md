# CLAUDE.md

This repository is the company's operating system — process documentation,
not code. It defines how decisions are made (RFDs), how releases ship, what
procedures exist (playbooks), and current policy (handbook). Work *inside*
these processes, not around them.

## Layout

- `rfd/NNNN/README.md` — numbered decision records (Oxide-style), states:
  prediscussion → ideation → discussion → published → committed / abandoned
- `handbook/` — current policy; always reflects reality
- `playbooks/` — step-by-step procedures (trigger / owner / steps /
  escalation / done-when)
- `releases/` — release-train process; `releases/cycles/` archives past cycles
- `finance/` — vendor register and monthly review one-pagers (records, not process)

## Hard rules

1. **Never rewrite a published/committed RFD to match new reality.** RFDs are
   history. Write a superseding RFD and cross-link both. Only metadata
   (`state:`, `discussion:`) and typo fixes may change after publish.
2. **Consequential process changes require an RFD**, not a direct edit:
   reserve the next number (check the index in `rfd/README.md` AND existing
   `rfd/` dirs for the true max), copy `rfd/templates/template.md` to
   `rfd/NNNN/README.md`, zero-pad to 4 digits.
3. **Every RFD state change updates the index table in `rfd/README.md`** in
   the same commit. Same for new playbooks (`playbooks/README.md` index) and
   new handbook pages (`handbook/README.md` contents table).
4. **Typo/clarity fixes go direct to handbook/playbooks; policy changes go
   through an RFD first.** When an RFD publishes, update the affected
   handbook/playbook pages in the same breath and note it in the RFD's
   implementation section.
5. **New recurring rituals must register in `handbook/operating-cadence.md`**
   — a review/meeting not on that page doesn't exist. Adding one means naming
   what it replaces (or an RFD arguing for growth).
6. **Playbooks keep their skeleton**: Trigger / Owner / Last verified /
   Before you start / Steps (numbered, imperative) / Escalation / Done when —
   ending with the "if a step was wrong, PR the fix" checkbox. Update
   `Last verified:` when a playbook is meaningfully revised or actually run.
7. **Cross-link, don't duplicate.** Policy lives in exactly one place;
   everywhere else links to it. If two pages disagree, that's a bug — fix the
   non-authoritative one.

## Current state (update when it changes)

- RFDs 0001–0004 published (process adoption); **0005 (compensation) and
  0006 (business direction) are in ideation awaiting founder decisions** —
  several pending processes (sales pipeline, support, roadmap intake)
  deliberately wait on 0006's outcome.
- The hiring playbook hard-blocks on RFD 0005 reaching published.
- Git: work on `main` is acceptable while the team is one person;
  RFD branches (`rfd/NNNN`) + PRs become the rule once there's a remote and
  a second contributor.

## Style

- Markdown, ~78-column wrap, sentence-case headings.
- Tables for indexes and role/ritual maps; prose for reasoning.
- Templates live in `*/templates/`; copy them, don't edit them in place
  (template improvements are their own PRs).
