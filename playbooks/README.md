# Playbooks

Step-by-step procedures for situations that recur or that are too important to
improvise. If the handbook says *what we believe and decide*, and RFDs record
*why*, playbooks say *exactly what to do, in order, at 3 a.m., by someone
doing it for the first time*.

## Rules

1. **If you did it twice, write the playbook** (or add the missing steps to
   an existing one). The third run should require no tribal knowledge.
2. **The runner updates the playbook.** Every execution that hits a wrong,
   missing, or confusing step ends with a PR fixing it. A playbook nobody
   amends is a playbook nobody follows.
3. **Playbooks are checklists, not essays.** Numbered steps, exact commands,
   exact links, named owners. Background belongs in the handbook or an RFD —
   link to it.
4. **Contentious changes go through an RFD; corrections go through a PR.**
   Fixing a wrong command needs no ceremony.

## Anatomy

Every playbook (see [`templates/playbook-template.md`](templates/playbook-template.md)) has:

- **Trigger** — the situation that means "run this now"
- **Owner** — the role accountable for the playbook staying correct
- **Steps** — numbered, imperative, copy-pasteable
- **Escalation** — who to wake, and when to stop following the script
- **Done when** — the observable end state

## Index

| Playbook | Trigger |
|---|---|
| [incident-response.md](incident-response.md) | Production/customer-impacting incident |
| [customer-onboarding.md](customer-onboarding.md) | New customer signed |
| [hiring.md](hiring.md) | A role is opened |
| [monthly-financial-review.md](monthly-financial-review.md) | First week of each month |

*(Add rows as playbooks are written. Likely next: offboarding, security
incident, press/comms response, RMA & returns for hardware.)*
