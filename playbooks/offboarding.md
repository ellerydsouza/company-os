# Playbook: Offboarding

**Trigger:** A departure is decided — resignation accepted or termination
decided. Run starting the **same day**, whatever the circumstances.
**Owner:** The departing person's manager (founder until delegated)
**Last verified:** 2026-08-06 (initial draft)

## Before you start

- Access: the [access inventory](../handbook/security.md#the-access-inventory),
  payroll/benefits admin, cap-table tool.
- Tone check: most departures are good departures. Run the same checklist
  with the same care either way — alumni talk, and how people leave is how
  your employer brand is built. For involuntary exits, compress steps 2–4
  into the same day and have comms ready *before* the conversation.

## Steps

1. **Agree the story and the date.** With the person (when voluntary): last
   day, what's announced, by whom, when. Ambiguity here breeds rumor.
2. **Revoke access from the inventory, not from memory.** Walk the access
   inventory line by line: revoke or transfer each entry, initial and date
   it. Then the classics that hide outside inventories: API keys and tokens
   they created, shared-vault memberships, OAuth grants, repo deploy keys,
   their email (forward to manager for 90 days, then close).
3. **Knowledge handoff before the last day:** a written page per owned area
   — current state, open threads, where the bodies are buried — plus a live
   walkthrough of anything operational. Every playbook they own gets a new
   named owner *in the same PR*.
4. **Equipment and admin:** hardware returned or wiped remotely; final
   payroll and expenses settled; equity paperwork (vesting stop, exercise
   window, deadlines) delivered **in writing** — surprising someone about an
   exercise window later is unforgivable.
5. **Announce** per the agreed story — team first, then any affected
   customers with their new point of contact.
6. **Exit conversation** (voluntary exits): 30 minutes, real questions —
   what should we fix, what nearly kept you. File the notes; feed anything
   systemic into the quarterly retro.
7. **Close out:** reconcile the access inventory one final time (goal: their
   name appears nowhere), update the team page/CRM ownerships, mark the
   departure date in payroll/cap-table records.

## Escalation

- Any sign of data exfiltration or sabotage risk: run step 2 *first*, before
  any conversation, and loop in legal counsel — this is the one case where
  the order inverts.
- Disputed equity/comp on exit: founder + counsel; nothing improvised in
  writing.

## Done when

- Access inventory shows zero entries for the person, handoff pages merged,
  equipment settled, paperwork delivered, announcement made.
- [ ] If any step was wrong, missing, or confusing: open a PR fixing this
  playbook before you close the task.
