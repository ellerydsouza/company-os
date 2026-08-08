# Requests for Discussion (RFDs)

RFDs are how we propose, discuss, and record decisions of consequence. The
process is modeled on [Oxide Computer's RFD
process](https://oxide.computer/blog/rfd-1-requests-for-discussion), which in
turn descends from the IETF's RFC tradition.

The full process is defined in [RFD 0001](0001/README.md) — which is itself an
RFD, so the process can be changed through the process.

## Quick start

1. **Reserve a number.** Find the highest existing number under `rfd/` and
   take the next one (zero-padded to 4 digits, e.g. `0007`).
2. **Branch.** `git checkout -b rfd/0007`
3. **Draft.** `mkdir rfd/0007 && cp rfd/templates/template.md rfd/0007/README.md`
   Set `state: prediscussion` (or `ideation` if you only have the shape of an
   idea and want a co-author).
4. **Push early.** Push the branch as soon as the metadata is filled in — this
   is what reserves the number publicly.
5. **Open a PR when ready for feedback.** Set `state: discussion` and put the
   PR link in the `discussion:` field. Discussion runs **3–5 business days**
   by default.
6. **Merge on convergence.** Set `state: published`. Later, when the decision
   is fully implemented and reality matches the document, update to
   `state: committed`. Dead ends get `state: abandoned` (also merged — a
   documented dead end is valuable).

## Index

| RFD | Title | State |
|---|---|---|
| [0001](0001/README.md) | The RFD process | published |
| [0002](0002/README.md) | Release management process | published |
| [0003](0003/README.md) | Operating cadence and first domain processes | published |
| [0004](0004/README.md) | Security baseline, offboarding, and vendor register | published |
| [0005](0005/README.md) | Compensation philosophy | ideation |
| [0006](0006/README.md) | Business direction — software, physical product, or both | ideation |
| [0007](0007/README.md) | Engineering platform and practice (adopting k8s-project-playbook) | published |
| [0008](0008/README.md) | Engineering onboarding — structural proactivity and the golden path | discussion |
| [0009](0009/README.md) | Mission, principles, and values | ideation |
| [0010](0010/README.md) | Materials-based hiring and public job descriptions | ideation |
| [0011](0011/README.md) | LLM and AI-agent use policy | ideation |
| [0012](0012/README.md) | Record every meeting | ideation |

*(Update this table when merging an RFD.)*

## Parked candidates (no number reserved yet)

Ideas from the [Oxide public RFD](https://rfd.shared.oxide.computer/) scan
(2026-08-07) that wait on a trigger; reserve a number when the trigger hits:

- **Focus day** (meeting-free weekday, Oxide RFD 83) — trigger: first hire.
- **Phases of engineering + "determination"** (Oxide RFDs 5, 113) —
  trigger: first substantial engineering effort; also a candidate
  enrichment for `handbook/decision-making.md`.
- **Partnership as shared values** (Oxide RFD 68) — trigger: RFD 0006
  chooses hardware, or first strategic supplier/partner.
- **Open source policy** (Oxide RFD 224: MPL 2.0 default, license tiers,
  no CLAs) — trigger: RFD 0006 chooses software, or first public repo with
  contributions.
- **Pull-based cadence for optional rituals** (Oxide RFD 38's journal-club
  mechanism: fires only when ≥2 people commit) — trigger: first optional
  recurring ritual added to the operating cadence.
