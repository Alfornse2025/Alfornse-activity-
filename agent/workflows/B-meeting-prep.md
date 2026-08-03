# WORKFLOW B — Meeting prep

**Trigger:** Any meeting in the next three working meetings; on demand for a specific one.
**Produces:** a 5-minute prep card per meeting (`templates/meeting-prep-card.md`), attached to the brief or delivered standalone.

---

## Inputs

- The calendar invite: title, time, location, attendees, attached documents, RSVP state.
- The last **2 email threads** with each attendee.
- The most recent **Otter recording of the same meeting series**, if one exists — with its action items.
- Any Drive document named in the invite or produced for the last session.
- Open tracker rows owned by, or blocking, anyone in the room.

---

## Steps

1. **Establish the objective.** What must be true when the meeting ends that isn't true now? If the invite doesn't say and no thread implies it, the card says so — an unclear objective is itself the finding, and the first recommended question.

2. **Map the room.** For each attendee: what they want out of this meeting, what they last said or asked for, and what they are waiting on from Alfornse. Anyone with an open commitment either way is named.

3. **Carry forward.** From the last session of this series: what was agreed, what was owed, what slipped. Anything Alfornse owns and hasn't done is stated plainly at the top of the card — better to see it here than hear it there.

4. **Anticipate.** The three most likely objections or pushbacks, each with a one-line answer. Where the answer needs data Alfornse doesn't have, say what to collect and by when.

5. **Draft three remarks.** Specific enough to say verbatim: the opening position, the concession that costs least, and the point that must land before the meeting ends.

6. **Draft three questions.** Ones that surface commitment, cost or timing — not ones already answered in the papers.

7. **Name the one outcome** that makes attendance worth the hour. If none exists, say so and recommend declining or delegating — that is a legitimate output of this workflow.

8. **Attach.** List the documents to have open, and flag any SENSITIVE material so it isn't carried into a shared screen or a summary.

9. **Income lens.** If an attendee or agenda item touches `opportunities/INCOME-OPPORTUNITIES.md`, name the register entry (`O-xx`) and the one thing to notice in the room. Never a pitch — a listening instruction. Where the meeting is KRA business, the conflict-of-interest boundary in `agent/BOUNDARIES.md §5` applies and is stated on the card.

---

## Output shape

The card is one page and fits a phone screen before the meeting starts. Order: objective → the room → carried forward → 3 remarks → 3 questions → likely objections → the one outcome → attachments → risk flags.

---

## Prompt

> Prepare a 5-minute prep card for [meeting]. Pull the invite, the last two email threads with each attendee, the most recent Otter recording of this series with its action items, any named Drive documents, and every open tracker row involving the people in the room. Give me: the objective, who wants what, what was carried forward from last time (including anything I owe and haven't done), three remarks I can say verbatim, three questions that surface commitment or timing, the three most likely objections with answers, and the one outcome that makes this meeting worth attending. If there isn't one, say so and tell me to decline. Flag any SENSITIVE material and any conflict-of-interest exposure.
