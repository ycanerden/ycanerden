# Set up the company in the Automations tab

Cursor cannot create automations from this PR. You paste these into [cursor.com/automations](https://cursor.com/automations). Five minutes each.

Connect first:

1. **This repo** as the automation repository (`ycanerden/ycanerden`)
2. **Gmail** (already working here — keep it)
3. **X** — Settings → MCP → X. Required before any live posting or reply runs
4. Optional: Slack, Notion

Create each automation as **Private**. Repository: **single repo** `ycanerden/ycanerden` on `main` (or this branch until merged). Enable **Memories**. Enable **MCP** for Gmail and X.

Cron times below are written for **Europe/Brussels**. In the UI, set timezone to Brussels or prefix cron with `CRON_TZ=Europe/Brussels`.

## 1. Daily content engine

| Field | Value |
| --- | --- |
| Name | Can Inc — daily content |
| Trigger | Schedule · weekdays 07:30 |
| Cron | `CRON_TZ=Europe/Brussels 30 7 * * 1-5` |
| Prompt | Paste `automations/daily-content.md` |

## 2. Opportunity radar

| Field | Value |
| --- | --- |
| Name | Can Inc — opportunity radar |
| Trigger | Schedule · daily 12:10 |
| Cron | `CRON_TZ=Europe/Brussels 10 12 * * *` |
| Prompt | Paste `automations/opportunity-radar.md` |

## 3. Weekly GTM review

| Field | Value |
| --- | --- |
| Name | Can Inc — weekly GTM |
| Trigger | Schedule · Sunday 18:00 |
| Cron | `CRON_TZ=Europe/Brussels 0 18 * * 0` |
| Prompt | Paste `automations/weekly-gtm.md` |

## 4. Ship to post

| Field | Value |
| --- | --- |
| Name | Can Inc — ship to post |
| Trigger | GitHub · **Push to branch** on `ycanerden/habitat-bunny`, `ycanerden/mesh`, `ycanerden/habitat-skills` (add this repo too if you want profile updates) |
| Prompt | Paste `automations/ship-to-post.md` |

If one automation cannot watch three repos, create one per repo or use a multi-repo environment.

## 5. X engage (only after X MCP is connected)

| Field | Value |
| --- | --- |
| Name | Can Inc — X engage |
| Trigger | Schedule · weekdays 19:00 |
| Cron | `CRON_TZ=Europe/Brussels 0 19 * * 1-5` |
| Prompt | Paste `automations/engage.md` |

Keep `PUBLISH_MODE=off` until you trust the drafts for a week.

## How you work with the agents

1. Automation opens a PR or emails you a Gmail **draft**
2. You edit in 5 minutes or reply on the PR: `APPROVED` / `rewrite` / `kill`
3. You paste LinkedIn yourself
4. When ready, flip X to `PUBLISH_MODE=on` for approved items only

## Manual trigger

Any time: open a cloud agent on this repo and say:

> Run `automations/daily-content.md` for today. Do not publish.

That is the same company, without the schedule.
