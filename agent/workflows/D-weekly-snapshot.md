# WORKFLOW D — Weekly strategic snapshot

**Trigger:** Sunday 18:00 EAT, alongside the existing weekly plan ritual.
**Produces:** a one-page snapshot appended to `templates/weekly-review.md`'s structure, a cleaned tracker, and an updated opportunity register.
**Time budget:** 30 minutes of the principal's time, of which the agent's output is a 5-minute read.

---

## Inputs

- The week's briefings (`briefings/`), to compare planned against done.
- `tracker/ACTION-TRACKER.md` — all rows, all statuses.
- `opportunities/INCOME-OPPORTUNITIES.md`.
- Next week's calendar, both accounts.
- `agent/MEMORY.md` and `agent/AUDIT-LOG.md`.

---

## Steps

1. **Scorecard.** Per bucket (A/B/C): planned, done, slipped — and for each slip, the actual cause. Distinguish *didn't get to it* from *blocked by someone else* from *shouldn't have committed to it*. The third kind is the one worth acting on.

2. **Tracker hygiene.**
   - Mark `Done`; move items completed over a month ago to the archive.
   - Every `Waiting` row: is it waiting on the right person, and has the chase happened? Chase, escalate, or drop with a reason.
   - Every row with no due date gets one or is dropped deliberately.
   - Every row untouched for three weeks: still real? Say so or archive it.

3. **Top 3 risks.** What could go materially wrong in the next two weeks — a deadline that will not be met at the current rate, a dependency with no owner, a commitment made in a room and never scheduled. Each with a mitigation and an owner. Risks are named concretely, not as themes.

4. **Next week's Big 3.** One per bucket, each with the slot in next week's calendar where it will actually happen. A Big 3 item with no calendar slot is a wish.

5. **Calendar shape.** Next week's conflicts resolved? Protected slots intact? At least one deep-work block reserved for the hardest deliverable? Unanswered invitations answered?

6. **Opportunity movement.** Every `Pursue`/`Develop` entry: did it advance this week — yes or no, and what is the single next action? Promote (`Watch` → `Develop`) or park explicitly. A register entry that has not moved in three weeks is either parked or given a slot.

7. **KPI check** against `agent/CHIEF-OF-STAFF.md §9`: brief length, triage accuracy, conflicts caught before the day, closure rate, dropped-action count, average daily rating.

8. **One lesson.** What about how the week ran should change how next week is planned. One sentence, actionable, aimed at the system rather than at effort.

---

## Output shape

Scorecard table → 3 risks with mitigations → Big 3 with calendar slots → calendar shape → opportunity movement → KPI line → one lesson. Nothing else.

---

## Prompt

> Run the weekly strategic snapshot. Compare this week's briefings against the tracker: what was planned, what got done, what slipped and why — distinguishing "didn't get to it" from "blocked" from "shouldn't have committed". Run tracker hygiene: close, chase, date or drop every row. Give me the top 3 risks for the next two weeks with mitigations and owners, the Big 3 for next week (one per bucket, each with the calendar slot where it will happen), the state of next week's calendar shape, and movement on every `Pursue`/`Develop` opportunity. Check the KPIs. Finish with one lesson about how the week ran. Propose calendar changes; make none.
