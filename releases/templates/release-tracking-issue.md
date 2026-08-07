# Release vX.Y — cycle tracking

<!-- Copy this at cycle start. One issue/file per cycle. Check items off as
they complete; log every deviation inline under the phase where it happened.
This document is the checklist, the record, and the next lead's handoff. -->

**Release lead:** _name_ (shadow: _name_)
**Signal/quality:** _name_ · **Docs:** _name_ · **Comms:** _name_ · **Branch manager:** _name_
**Target launch date:** _YYYY-MM-DD_
**Cycle scope doc / milestone link:** _link_

---

## Phase 0 — Planning (week 0)

- [ ] Roles assigned and every hat above has a name on it
- [ ] Previous cycle's retrospective actions reviewed; carried-over items listed below
- [ ] Candidate scope collected from product/eng and written into the milestone
- [ ] **SCOPE FREEZE** declared (date: ______)
- [ ] Calendar of freezes/launch shared with the whole company

## Phase 1 — Build (weeks 1–3)

- [ ] Weekly scope check #1 — anything at risk flagged and cut/deferred early
- [ ] Weekly scope check #2
- [ ] Weekly scope check #3
- [ ] Docs impact list started (what will need writing/updating)
- [ ] *(hardware)* Supplier lead times and long-poles reviewed weekly

## Phase 2 — Stabilize (week 4)

- [ ] **FEATURE FREEZE / DESIGN FREEZE** declared (date: ______)
- [ ] Release branch cut *(software)* / EVT exit review held *(hardware)*
- [ ] CI/test signal green, or every red item has an owner and a deadline
- [ ] Exception requests logged below (feature freeze exceptions)

## Phase 3 — Harden (week 5)

- [ ] **CODE FREEZE / TOOLING FREEZE** declared (date: ______)
- [ ] Release candidate 1 built and validated *(software)* / DVT build reviewed *(hardware)*
- [ ] Docs and changelog complete and reviewed
- [ ] Announcement drafted; comms plan (channels, timing) agreed
- [ ] Support/success team briefed on what's changing
- [ ] Known-issues list written (empty is a claim, not a default)

## Phase 4 — Ship (week 6)

- [ ] Go/no-go held (attendees: ______; decision: ______)
- [ ] Released / MP go given
- [ ] Announcement out; customers notified
- [ ] Post-launch monitoring window complete (____ hours); incidents: ______

## Phase 5 — Close (week +1)

- [ ] Retrospective held ([template](retrospective.md)); notes linked: ______
- [ ] Retro actions filed as PRs/RFDs/issues (links: ______)
- [ ] This document moved to `releases/cycles/` and linked from the next cycle
- [ ] Handoff conversation with next release lead done

---

## Exception log

| Date | Requested by | What | Freeze breached | Risk | Decision |
|---|---|---|---|---|---|
| | | | | | |

## Deviations & notes

<!-- Anything that didn't go per the template — this is the most valuable
section for your successor. Include what you'd change about this template. -->
