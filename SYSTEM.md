# SYSTEM — How the Action Tracker & Briefing System Works

Timezone: Africa/Nairobi (EAT, UTC+3). All times below are EAT.

## 1. Data sources (what feeds the system)

| Source | What is pulled | Used for |
|---|---|---|
| Google Calendar — `alfornse@gmail.com` | Today + 7-day lookahead, all events | Schedule, conflicts, deadline events |
| Google Calendar — `cose.statehouse@gmail.com` | Same window | State House / PSEO commitments |
| Otter.ai | Recordings since the last briefing: AI summaries + **action items** | New actions into the tracker; meeting follow-ups |
| Gmail | Unread inbox, last 96h, noise filtered | Urgent items, meeting requests, deadlines |
| Google Drive | Recently modified working documents | Work-in-progress context; deliverable status |
| iCloud | Not directly connectable from this environment — mirrored via the workflow in `docs/ICLOUD-SYNC.md` | Personal notes, files created on Apple devices |
| Other AI tools (Claude, ChatGPT etc.) | Outputs saved into Drive or iCloud folders are picked up through those two channels | Draft deliverables, research |

## 2. Cadence (when things update)

| When | What happens |
|---|---|
| **Daily 05:00** | Automated session: scan all sources → write `briefings/YYYY-MM-DD-briefing.md` → refresh `tracker/ACTION-TRACKER.md` → commit & push |
| **Ad hoc** | After any significant meeting, its Otter action items are folded into the tracker at the next daily run (or on demand) |
| **Sunday 18:00** | Weekly plan ritual (already on the calendar) — review the week with `templates/weekly-review.md` |
| **Month-end** | Archive completed actions to the bottom of the tracker; prune stale opportunities |

## 3. The MECE framework

Top level — three mutually exclusive, collectively exhaustive buckets:

- **A. KRA** — Kenya Revenue Authority engagement
  - A1. Commissioner General directives & advisory work
  - A2. Executive Committee / departmental follow-ups
  - A3. External stakeholders (banks, vendors, development partners)
- **B. Personal**
  - B1. Family & relationships
  - B2. Health & energy
  - B3. MPP — Strathmore (classes, assignments, exams)
  - B4. Personal finance & admin
- **C. Other (ventures & income)**
  - C1. KRP Holding (Advisory, Technologies, Capital, Opportunities Fund)
  - C2. PSEO — President's Strategy & Execution Office
  - C3. Farm & retail (Masinga Farm; Neon & Nexus)
  - C4. Land & property (Kanyonyoo, Naivasha/Azu SPV, Kithioko container homes)
  - C5. Income-opportunity pipeline (see `opportunities/INCOME-OPPORTUNITIES.md`)

Rules:
1. Every action is tagged with exactly one sub-bucket (e.g. `A2`, `C5`).
2. If an item seems to fit two buckets, the bucket of the **primary beneficiary** wins (e.g. a KRA meeting that could become KRP business is `A` until the KRA obligation is discharged; the opportunity is logged separately under `C5`).
3. "Waiting on others" is a status, not a category — actions keep their bucket.

## 4. Action tracker conventions

Each action row: `ID | Action | Owner | Source | Due | Status`

- **ID**: bucket + running number (`A2-03`).
- **Source**: where it came from (Otter meeting title + date, calendar event, email).
- **Status**: `Open` → `In progress` → `Waiting` → `Done` (or `Dropped`, with a note).
- Actions are never deleted — `Done`/`Dropped` items move to the archive section at month-end so the diary doubles as a record of work.

## 5. Morning briefing structure

See `templates/morning-briefing.md`. Fixed order: (1) Top 3 priorities of the day, (2) Schedule with conflicts flagged, (3) MECE follow-up plan (A/B/C), (4) New inputs since yesterday (Otter/Gmail/Drive), (5) Income-opportunity watch, (6) One decision needed today.

## 6. Confidentiality tiers (mirrors the Drive charter)

- **Tier 1 — KRA privileged**: taxpayer-identifiable or CG-privileged material. Never written into this repository. Referenced only as "see meeting X".
- **Tier 2 — business confidential**: KRP client work, deal terms. Action-level references only.
- **Tier 3 — personal/routine**: may be recorded normally.
