# WORKFLOW C — Post-meeting follow-up

**Trigger:** A new Otter recording appears, or notes are handed to the agent. Runs at the next morning pass, or on demand immediately after a significant meeting.
**Produces:** tracker rows, a follow-up email draft, and — where the meeting created a commercial signal — an opportunity-register update.

**Principle:** a decision taken in a room and not written down did not happen. This workflow is the difference between a system and a diary.

---

## Inputs

- Otter recording: AI summary, action items, and the transcript where a commitment's wording matters.
- The prep card, if Workflow B ran — so intended outcomes can be compared with actual ones.
- The existing tracker, to avoid duplicate rows.

---

## Steps

1. **Extract decisions.** What was actually decided, as distinct from discussed. Each decision gets one line: what was decided, by whom, effective when.

2. **Extract action items.** Every commitment made by anyone in the room. For each, capture the exact wording where it matters — "circulate the bank list" is a different obligation from "confirm the bank list".

3. **Assign owner and bucket.**
   - Alfornse named as owner → tracker row, status `Open`, real due date.
   - Someone else named → tracker row, status `Waiting`, with the chase date (not the delivery date) in the due column.
   - Nobody named → propose an owner and flag it: unowned actions are how deliverables die.

4. **Propose deadlines.** Real ones, derived from what was said in the room, the next session of the series, or the dependency behind the item. Never "TBD". If the meeting genuinely set no date, propose one and mark it as the agent's proposal.

5. **De-duplicate.** Match against open tracker rows. An existing row gets updated — new source, new date, changed status — rather than a second row with a different ID.

6. **Compare to the prep card.** Did the intended outcome land? If not, what changed in the room, and does that alter anything else in the tracker?

7. **Draft the follow-up email.** Decisions, owners, dates, and one explicit ask (usually "confirm the above"). Short. Three tones available (`templates/email-reply-drafts.md`); default to short for internal, diplomatic for external counterparties. **Draft only.**

8. **Opportunity signal.** Anything in the meeting that advances an entry in `opportunities/INCOME-OPPORTUNITIES.md` → update the register's next-action line. Apply the conflict-of-interest wall (`agent/BOUNDARIES.md §5`): the KRA obligation stays in bucket A; only the generalisable commercial angle is logged in C5.

9. **Confidentiality pass.** Before anything is written to the repository: Tier-1 KRA material and SENSITIVE detail are reduced to action-level references. The transcript stays in Otter. Figures, taxpayer detail and named-individual assessments do not enter the tracker.

10. **Log** the draft and any proposals in `agent/AUDIT-LOG.md`.

---

## Quality gates

- Every action item spoken in the meeting appears exactly once in the tracker, or is explicitly recorded as not-an-action with a reason.
- No row has a blank owner or a blank due date.
- No Tier-1 material has entered the repository.
- The follow-up draft names owners and dates, and contains exactly one ask.

---

## Prompt

> Process [meeting / Otter recording] with Workflow C. Extract decisions and every action item; assign bucket, owner and a real due date to each; mark items owned by others as `Waiting` with a chase date. De-duplicate against the existing tracker and update rather than duplicate. Compare against the prep card if one exists. Draft a short follow-up email listing decisions, owners and dates with one clear ask — draft only, do not send. Update `opportunities/INCOME-OPPORTUNITIES.md` if the meeting moved anything, respecting the KRA/KRP conflict wall. Keep Tier-1 material out of the repository — action-level references only. Log the draft in the audit log.
