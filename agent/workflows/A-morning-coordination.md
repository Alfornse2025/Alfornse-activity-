# WORKFLOW A — Morning coordination run

**Trigger:** Daily 05:00 EAT (or on demand: *"Run the morning coordination pass"*).
**Produces:** `briefings/YYYY-MM-DD-briefing.md`, a refreshed `tracker/ACTION-TRACKER.md`, prep cards for the next three meetings, reply drafts for urgent mail.
**Time budget:** the output must be a 3–5 minute read. Everything below serves that constraint.

---

## Inputs

| Source | Window | Notes |
|---|---|---|
| Google Calendar `alfornse@gmail.com` | Today + 7-day lookahead | All events, including declined and unanswered |
| Google Calendar `cose.statehouse@gmail.com` | Same | State House / PSEO |
| Otter.ai | Recordings since the last briefing | Summaries **and** action items |
| Gmail | Unread, last 96h | Noise filtered, not deleted |
| Google Drive | Recently modified | Working documents only |
| This repo | Current state | Tracker, opportunities, `agent/MEMORY.md` |

If a source is unreachable, the brief says so in the header line. Never silently omit a source.

---

## Steps

1. **Read memory first.** `agent/MEMORY.md` — standing priorities, protected slots, stakeholder notes, standing approvals. This is what makes the Top 3 correct rather than merely urgent.

2. **Pull calendar (both accounts).** Build the 7-day view. Mark: conflicts, unanswered invitations, anything landing on a protected slot, and meetings with no preparation done.

3. **Pull Otter recordings since the last run.** Extract action items. For each: is Alfornse the **owner** or a **monitor**? Owner items become tracker rows with dates; monitor items become chases.

4. **Triage Gmail (96h).** Classify each thread: bucket + class + one-sentence justification. Aggregate PARK into a single count. Flag SENSITIVE and stop on those items.

5. **Scan Drive** for changed working documents — what is in flight, what is waiting for review.

6. **Reconcile against the tracker.** Every open row: still live? overdue? blocked on a person who can be chased today? Every new action item from steps 3–4 becomes a row with ID, owner, source, due, status. **Nothing from a meeting is allowed to exist only in the brief.**

7. **Select the Top 3.** Rank by `MEMORY.md §1`, then by deadline proximity, then by how many other things unblock. Each cites its tracker ID. If two candidates tie, the one that unblocks another person wins.

8. **Find the one decision.** The single choice that, unmade, blocks the most. Frame it as two options with a recommendation and a confidence level. One decision — not three.

9. **Write prep cards** for the next three working meetings (`templates/meeting-prep-card.md`).

10. **Draft replies** for DECIDE and DO mail in three tones (`templates/email-reply-drafts.md`). Create them as Gmail drafts. Send nothing.

11. **Write the brief** to `briefings/YYYY-MM-DD-briefing.md` from `templates/morning-briefing.md`. Fixed six-section order.

12. **Log** every draft and proposal in `agent/AUDIT-LOG.md`. Commit and push.

---

## Quality gates — do not ship the brief if

- Any Top-3 item lacks a tracker ID.
- Any Otter action item owned by Alfornse has no corresponding tracker row.
- A calendar conflict exists in the next 7 days and is not flagged with a proposed resolution.
- Section 6 contains more than one decision, or a decision with no recommendation.
- A number is asserted without its source.
- The brief runs past a 5-minute read.

---

## Prompt

> Run the morning coordination pass. Read `agent/MEMORY.md` first. Pull both calendars (today + 7 days), Otter recordings since the last briefing, unread Gmail (96h) and recently modified Drive documents. Classify everything by MECE bucket and handling class; flag and stop on SENSITIVE items. Reconcile every owned action item into `tracker/ACTION-TRACKER.md`. Then write `briefings/<today>-briefing.md`: Top 3 priorities with tracker IDs, schedule with conflicts flagged and resolutions proposed, MECE follow-up plan, new inputs, income-opportunity watch, and one decision framed as two options with a recommendation and confidence. Add prep cards for my next three meetings and three-tone reply drafts for anything urgent. Draft only — send nothing, move nothing. Log proposals in `agent/AUDIT-LOG.md`, then commit and push.
