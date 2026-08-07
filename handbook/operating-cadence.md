# Operating cadence

The single calendar of the company's recurring rituals. **If a recurring
review or meeting is not on this page, it does not exist.** Every process
adopted later must register its rituals here in the same PR.

Each ritual names one owner. The owner's job is that the ritual *happens and
produces its output* — not necessarily to run it. Skipping is sometimes right
(launch week, holidays) but must be said out loud in chat, not silent; the
quarterly retro counts the skips.

## Weekly

| Ritual | Owner | Inputs | Output |
|---|---|---|---|
| **Business review** (30 min): the 3–5 core metrics, sales pipeline, top risks | CEO | Metrics dashboard, pipeline list | Decisions + action owners noted in chat |
| **Release scope check** (part of the [release cycle](../releases/README.md)) | Release lead | Cycle tracking issue | Updated tracking issue; at-risk items cut early |

## Monthly

| Ritual | Owner | Inputs | Output |
|---|---|---|---|
| **Financial review** ([playbook](../playbooks/monthly-financial-review.md)) | CEO | Bank balances, bookkeeper close, budget | One-pager in `finance/reviews/YYYY-MM.md` |
| **Goals check** (15 min): each quarterly goal — on track / at risk / abandoned, one sentence why | CEO | Quarterly goals doc | Status annotations on the goals doc |

## Quarterly

| Ritual | Owner | Inputs | Output |
|---|---|---|---|
| **Planning**: set next quarter's 3–5 goals; kill or re-justify everything else | CEO | Last quarter's goals + metrics + roadmap intake | Goals doc for the quarter (RFD if direction changes materially) |
| **Operating-system retro**: are the processes in this repo working? Skipped-ritual count, stale RFD states, playbooks nobody updated | Rotating | This repo, chat archaeology | PRs/RFDs amending the processes |
| **Board/investor update** *(once applicable)* | CEO | Financial reviews, goals, metrics | Sent update, archived |

## Annual

| Ritual | Owner | Inputs | Output |
|---|---|---|---|
| **Compensation review** (all roles at once, not ad hoc) | CEO | Comp philosophy RFD, market data | Adjustments + updated bands |
| **Vendor/contract & insurance review** | Ops owner | Vendor register, renewal dates | Renewals decided, register updated |
| **Strategy review**: is the plan still the plan? | CEO | The year's financial reviews and retros | RFD if the answer is no |

## Rules

1. Rituals produce **written outputs in a fixed place**, listed above. A
   review with no artifact didn't happen.
2. Keep the total ceremony small. Adding a ritual to this page requires
   naming which existing one it replaces, or an RFD arguing the calendar
   should grow.
3. At current (founder-only/tiny) scale, several rituals collapse into one
   sitting — fine. The outputs still get produced separately, because the
   *artifacts* are what scale to a team, not the meeting.
