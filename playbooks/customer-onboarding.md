# Playbook: Customer onboarding

**Trigger:** A new customer has signed (contract executed or self-serve
upgrade to a paid tier that includes onboarding).
**Owner:** Whoever owns customer success (founder until delegated)
**Last verified:** 2026-08-06 (initial draft — verify against first customers
and replace placeholder steps with your product's specifics)

## Before you start

- Access required: CRM, provisioning/admin panel, shared-channel tooling
  (Slack Connect / email thread), <fulfillment system — hardware>.
- Have at hand: signed order details, the promises made during the sale
  (read the CRM notes — onboarding is where sales promises go to be honored
  or forgotten).

## Steps

1. **Within 1 business day of signature:** send the welcome message —
   named point of contact, what happens next, and the kickoff scheduling
   link. Log the date in the CRM.
2. **Provision** the account/tenant (or enter the fulfillment order and
   confirm the ship date — hardware). Verify by logging in as/with the
   customer's first user, not just by seeing "created".
3. **Kickoff call** within the first week: their success criteria in their
   words (write these in the CRM verbatim), key contacts both sides,
   timeline. Their success criteria — not our feature list — define
   "onboarded".
4. **First-value milestone:** define, from the kickoff, the one observable
   event that means the customer got real value (first successful workflow,
   first device deployed in the field). Target date: ____. Track it in the
   CRM; this is the number onboarding is judged on.
5. **Check-in cadence** until first value: weekly, owned by the point of
   contact. A silent new customer is a churning customer.
6. **30-day review:** did they hit first value? If yes — ask for feedback
   and log expansion signals. If no — escalate (below), don't extend the
   cadence and hope.
7. **Close onboarding** in the CRM; hand to the steady-state success
   cadence.

## Escalation

- Customer unresponsive for 2 weeks, or first value clearly slipping past
  the 30-day mark: escalate to the founder/sales owner for a joint call.
- Promised-but-missing product capability discovered: log it against the
  roadmap and tell the customer the honest status — never silently hope.

## Done when

- First-value milestone hit and recorded, 30-day review done, CRM shows
  onboarding closed with dates.
- [ ] If any step was wrong, missing, or confusing: open a PR fixing this
  playbook before you close the task.
