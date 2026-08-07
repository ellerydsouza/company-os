# Playbook: Monthly financial review

**Trigger:** The first week of every month (on the
[operating cadence](../handbook/operating-cadence.md)), once the previous
month's bookkeeping close is available.
**Owner:** CEO
**Last verified:** 2026-08-06 (initial draft)

## Before you start

- Access: bank account(s), bookkeeping system / bookkeeper's close package,
  the budget/plan spreadsheet, last month's review in `finance/reviews/`.

## Steps

1. **Collect the raw numbers:** total cash across all accounts (as of the
   1st), the month's money in (revenue actually received) and money out, and
   any committed-but-unpaid items large enough to matter (tax bills, annual
   contracts, tooling payments — hardware deposits especially).
2. **Compute burn and runway.** Net burn = money out − money in.
   **Runway = cash ÷ trailing-3-month average net burn** — always the
   3-month average, never the best recent month; one good month is not a
   trend.
3. **Compare against plan.** For each budget line that deviates >15%, write
   one sentence: why, and whether it repeats.
4. **Write the one-pager** to `finance/reviews/YYYY-MM.md` (template below).
   Keep it to one page — the discipline is in the compression.
5. **Apply the runway rule:**
   - **> 18 months:** note it, move on.
   - **12–18 months:** the one-pager must name what would extend it
     (revenue milestones, cuts, raise timing) — thinking starts here.
   - **< 12 months:** an explicit decision is now required — start the
     raise, cut to a longer runway, or reach profitability. Write the
     decision as an RFD. **Below 12 months without a written plan is the
     one state this playbook exists to prevent.**
6. **File and flag:** commit the one-pager; raise anything requiring action
   in the next weekly business review with a named owner.

## One-pager template (`finance/reviews/YYYY-MM.md`)

```markdown
# Financial review — YYYY-MM

Cash: $____ · Net burn (month): $____ · Burn (3-mo avg): $____
**Runway: ____ months** (rule band: >18 / 12–18 / <12)

## vs plan
| Line | Plan | Actual | Δ | Why (if >15%) |
|---|---|---|---|---|

## Upcoming lumpy costs (next 90 days)

## Runway actions (required if <18 months)

## Decisions needed
```

## Escalation

- Runway crosses **below 12 months**: this stops being a monthly ritual and
  becomes the company's top priority — RFD within two weeks.
- Numbers that don't reconcile (bank vs books): resolve with the bookkeeper
  before publishing the review; never publish numbers you don't believe.

## Done when

- One-pager committed to `finance/reviews/`, deviations explained, runway
  rule applied, actions owned.
- [ ] If any step was wrong, missing, or confusing: open a PR fixing this
  playbook before you close the task.
