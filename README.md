# Company Operating System

This repository is the process backbone for the company. It defines **how we
decide, how we ship, how we execute, and how we work** — before it defines what
we build. It is designed to work whether the business ships software, a
physical product, or both (the models it borrows from — Oxide's RFDs and
Kubernetes release management — come from a hardware company and an
open-source software project respectively).

## The four layers

| Layer | Directory | Question it answers | Changes via |
|---|---|---|---|
| **RFDs** | [`rfd/`](rfd/) | How do we make and record decisions? | The RFD process itself |
| **Release management** | [`releases/`](releases/) | How do we ship on a cadence without chaos? | RFD |
| **Playbooks** | [`playbooks/`](playbooks/) | What are the exact steps for situation X? | PR (RFD if the change is contentious) |
| **Handbook** | [`handbook/`](handbook/) | What is durably true about how we work? | PR (RFD for significant policy changes) |

## How the layers fit together

```
        idea / problem / disagreement
                    │
                    ▼
              ┌───────────┐   discussion on a PR,
              │    RFD    │   3–5 business days
              └───────────┘
                    │  published & committed
        ┌───────────┼───────────────┐
        ▼           ▼               ▼
   handbook     playbook        release
   (policy,     (repeatable     process
   values,      procedure)      (cadence,
   defaults)                    roles)
        │           │               │
        └───────────┴───────┬───────┘
                            ▼
                       execution
                            │
                            ▼
                 retrospectives → new RFDs
```

- An **RFD** is where a decision is *made*. It is a historical record: once
  published it is not rewritten to match reality; a new RFD supersedes it.
- The **handbook** and **playbooks** are where decisions *live*. They are
  always current, updated whenever an RFD commits to a change.
- The **release process** is the drumbeat that turns decisions into shipped
  work, and its retrospectives feed problems back into new RFDs.

## Rules of the road

1. **Decisions of consequence get an RFD.** If you would need a meeting to
   decide it, write it down instead. See [`rfd/0001`](rfd/0001/README.md).
2. **If you did it twice, write a playbook.** The third person to do the task
   should not need tribal knowledge.
3. **The handbook is the source of truth for policy.** If the handbook and a
   verbal agreement disagree, the handbook wins — fix the handbook if it's
   wrong, via PR.
4. **Ship on the train, not when it's perfect.** Features that miss a freeze
   catch the next release. The cadence is sacred; the scope is not.
5. **Everything here is changeable — through the process.** Even the process
   documents themselves. That is the point.

## Getting started

- New to the company → read [`handbook/onboarding.md`](handbook/onboarding.md)
- Have an idea or see a problem → reserve an RFD number
  ([`rfd/README.md`](rfd/README.md))
- Running a release → copy
  [`releases/templates/release-tracking-issue.md`](releases/templates/release-tracking-issue.md)
- About to do a risky/rare operation → check [`playbooks/`](playbooks/) first

## License

The contents of this repository are licensed under
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — see
[LICENSE](LICENSE). You may reuse and adapt any of it, with attribution.
