# Handbook

The handbook is the **current truth** about how this company works: policies,
norms, defaults, and expectations. It is public-to-the-company, versioned in
git, and always up to date — when reality changes (usually via an RFD), the
handbook changes in the same breath.

How it relates to the other layers:

- **RFDs** are the *history* — why things are the way they are. Never edit an
  RFD to match new reality; edit the handbook and link the superseding RFD.
- **Playbooks** are the *procedures* — exact steps for specific situations.
- The handbook is the *policy* — what's true in general.

**Change process:** typo/clarity fixes → direct PR. Policy changes → RFD
first, handbook PR when it's published. If the handbook and anyone's memory
disagree, the handbook wins; if the handbook is wrong, fix it — don't route
around it.

## Contents

| Page | What it covers |
|---|---|
| [decision-making.md](decision-making.md) | How decisions get made and who makes them |
| [communication.md](communication.md) | Channels, norms, and defaults for how we talk |
| [onboarding.md](onboarding.md) | A new person's first two weeks |
| [operating-cadence.md](operating-cadence.md) | The calendar of recurring rituals — weekly to annual |
| [security.md](security.md) | The security baseline everyone follows |
| [engineering.md](engineering.md) | Durable engineering conventions; mechanics link to [k8s-project-playbook](https://github.com/ellerydsouza/k8s-project-playbook) |

Pages to add as the company grows (each via RFD): values, compensation
philosophy (pending [RFD 0005](../rfd/0005/README.md)), remote/office policy,
expenses & travel, performance & feedback.
