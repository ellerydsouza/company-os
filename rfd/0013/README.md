---
rfd: "0013"
title: Individual weekly updates replace status meetings
authors:
  - Ellery D'Souza <edsouza99@gmail.com>
state: discussion
discussion: https://github.com/ellerydsouza/company-os/pull/1
---

# RFD 0013: Individual weekly updates replace status meetings

## Problem

The [operating cadence](../../handbook/operating-cadence.md) lists the
company's recurring rituals, every one of them owned by a role and producing
a company artifact. Nothing on that page says how an individual's week
becomes visible to their manager and peers.

Left unspecified, status defaults to the standup meeting: synchronous,
hostile to time zones, and recorded nowhere. That contradicts the
[communication](../../handbook/communication.md) default of "async first,
written first" and its instruction not to spend synchronous time on status.
It also has a quieter cost. When status lives only in meetings, a person's
work is known to whoever happened to be in the room and to whoever talks
most. Performance and peer reviews then measure visibility rather than
output, and remote or quiet people are rated on what reviewers can recall
instead of what shipped. A written record removes the recall step.

The same record is the fastest onboarding document a team can have: eight
weeks of updates tell a new person what the team actually does better than
any overview.

## Proposal

Add one ritual to the weekly cadence: **each person posts a weekly update**
in the team channel, on the same day each week, in a fixed shape:

```
Week of YYYY-MM-DD

Shipped
- what merged, deployed, or closed, with a link each

In progress
- what is underway and where it stands, with a link each

Blocked / need
- the fact and the ask: "PR 1234 waiting on review since Tuesday"

Next week
- what you intend to ship
```

Rules:

1. **Ten lines or fewer, links on every item.** Facts and links; no
   adjectives. The links are the evidence, so a reader can verify any line
   in one click.
2. **Same day, every week.** A skipped week is said out loud in the same
   channel ("no update this week, on leave"), never silent, per the
   cadence page's rule on skipping.
3. **Blocked means a fact and an ask**, not a complaint. The update is not
   the place to raise a blocker for the first time; blockers are raised the
   day they happen. The update records that they exist.
4. **Managers read and acknowledge.** A reaction is enough. An update nobody
   reads decays within a month.
5. **Reviews cite them.** Performance and peer reviews reference the
   updates. A reviewer who has read eight of them rates work, not memory.

This ritual **replaces the standup meeting** as the status mechanism, which
satisfies the cadence page's rule that a new ritual names what it replaces.
Teams that keep a standup keep it for blockers and coordination only, not
for going round the room.

The template lives at
[`handbook/templates/weekly-update.md`](../../handbook/templates/weekly-update.md).

## Alternatives considered

- **Standup meetings.** The default. Synchronous, timezone-hostile, nothing
  retained, and the loudest person's week is the best known. Rejected by
  the communication handbook's own defaults.
- **Status lives in the tracker only.** Tickets and PRs are the evidence
  but not the narrative; nobody reads a tracker to learn what a colleague
  did this week, and work that is not a ticket (reviews, investigations,
  help given) vanishes.
- **Monthly written reports.** Too coarse to catch a blocked week in time
  and too long to be read.
- **Manager-written team summaries.** Puts the writing on the wrong person
  and filters each individual's work through someone else's attention,
  which is the problem being fixed.
- **Nothing.** At one person the cost of nothing is zero. The habit is
  cheapest to start at one person and hardest to start at ten.

## Trade-offs and risks

- **Ten minutes per person per week.** Cheap, and it displaces a daily
  meeting.
- **Performative updates.** Mitigated by the line cap and the link
  requirement: a padded update is visibly padded.
- **Updates as the only channel.** They are not. Blockers, questions and
  decisions still go where [communication](../../handbook/communication.md)
  says they go; the update is a weekly index of them.
- **Nobody reads them.** The acknowledgement rule and the review-citation
  rule are the mitigations. If after a quarter they are not read, the
  operating-system retro should say so and this RFD gets superseded.
- **Where they live.** Chat is a lossy medium. The channel post is the
  habit; whether to archive updates somewhere durable is left open below.

## Implementation / rollout

When published, in the same change:

- `handbook/operating-cadence.md`: add the weekly update row to the Weekly
  table.
- `handbook/communication.md`: add "Individual weekly status" to the
  "Where things go" table.
- `handbook/onboarding.md`: add "post your first weekly update" to the
  first-week checklist.
- `handbook/templates/weekly-update.md`: the template above.

Marked `committed` after eight consecutive weeks of updates from everyone,
which at founder scale means eight from the founder.

## Open questions

- A durable archive: a thread per quarter, a page per person, or nothing
  beyond chat search? Decide after a quarter of posts, not before.
- Day of week. Friday afternoon records the week; Monday morning sets it
  up. Either works; the team picks one and keeps it.
- Whether RFD 0012 (record every meeting), if adopted, changes the
  calculus for keeping any standup at all.
