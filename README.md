# Alfornse — Action Tracker & Daily Direction System

A structured daily operating system for Alfornse Kisilu: a synced action-tracker diary, a MECE-structured morning briefing, and an income-opportunity register — generated from live sources (Google Calendar ×2, Otter.ai recordings, Gmail, Google Drive) and updated on a daily cadence.

## Repository map

| Path | What it is |
|---|---|
| `SYSTEM.md` | How the system works: sources, cadence, MECE framework, rules |
| `briefings/` | One morning briefing per day (`YYYY-MM-DD-briefing.md`) |
| `tracker/ACTION-TRACKER.md` | The master action tracker — single source of truth for open actions |
| `opportunities/INCOME-OPPORTUNITIES.md` | Income opportunity register with required resources |
| `templates/` | MECE templates for the briefing and the weekly review |
| `docs/ICLOUD-SYNC.md` | How to mirror this repository into iCloud Drive |

## The MECE frame (used everywhere)

Every briefing, tracker entry and follow-up plan is divided into three mutually exclusive, collectively exhaustive categories:

1. **KRA** — the Kenya Revenue Authority engagement (Advisor to the Commissioner General): directives, committee follow-ups, stakeholder meetings.
2. **Personal** — family, health, MPP studies (Strathmore), personal finance and admin.
3. **Other** — KRP Holding & subsidiaries, PSEO, farm & retail operations (Masinga, Neon & Nexus), land/property projects, and the income-opportunity pipeline.

Every action lives in exactly one category. Nothing is uncategorised.

## Daily rhythm

- **05:00 EAT — Morning briefing generated**: calendars, overnight Otter recordings, inbox and Drive are scanned; the day's briefing is written to `briefings/` and the tracker is refreshed.
- **During the day** — the tracker is the to-do reference; check items off in place.
- **Sunday 18:00 EAT — Weekly plan** (existing calendar ritual): use `templates/weekly-review.md`.

## Confidentiality

KRA Tier-1 material (taxpayer-identifiable data, privileged CG-office content) is **never** stored here — only action-level summaries. Full transcripts stay in Otter; full documents stay in Drive/iCloud.
