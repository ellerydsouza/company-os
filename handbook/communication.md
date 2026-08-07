# Communication

## Defaults

- **Async first, written first.** Default to a doc or a message someone can
  read in their own time. Synchronous time is expensive; spend it on
  ambiguity, relationships, and deadlocks — not status.
- **Public by default (internally).** Questions and decisions happen in
  public channels, not DMs, so context accrues to the company instead of to
  pairs of people. DMs are for personal/sensitive matters.
- **Durable beats ephemeral.** Chat is for coordination; anything worth
  keeping (decisions, designs, procedures) gets promoted to the right home:
  RFD, handbook, playbook, or the release tracking issue. Chat is where
  knowledge goes to die; treat it as a lossy medium.

## Where things go

| This… | …goes here |
|---|---|
| Decision + reasoning | RFD |
| Current policy/norms | Handbook |
| Step-by-step procedure | Playbook |
| Release state | The cycle's tracking issue |
| Coordination, quick questions | Chat |
| Customer-visible status | Status page / customer channels (see comms role in [releases](../releases/README.md)) |

## Response-time expectations

- Chat: same business day. Nobody is expected to watch chat in real time —
  urgent means phone/page, per the [incident playbook](../playbooks/incident-response.md).
- RFD review: within the discussion window. Silence during the window is
  consent.
- After-hours: no expectation of response except for the on-call/incident
  path. Sending late is fine; expecting late replies is not.

## Writing norms

Lead with the point. Say who needs to do what by when. Disagree with ideas
plainly and with people kindly. When a thread exceeds ~10 messages of real
disagreement, stop — that's an RFD or a call.
