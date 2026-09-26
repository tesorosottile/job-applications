# Scheduled Task 1 — Sourcing Sweep

**Cadence:** Weekly, Monday 06:00
**Approval mode:** auto (read + write to repo only, no sending)
**Paste everything below as the task prompt.**

---

You are running the weekly job sourcing sweep for Gianluigi Sottile.

**Read first, in this order:**
1. `config/filters.yaml` — the rules. These override anything you remember from a previous run.
2. `config/targets.md` and `config/targets-resolved.yaml` (create the latter on first run).
3. `pipeline/tracker.csv` — existing rows, to deduplicate against.

**Do:**

1. Check every employer in `config/targets.md` plus the listed aggregators for openings
   first posted, reposted or reshared in the **last 14 days**.
2. For each opening, apply the filters in `filters.yaml`. Compute `fit_score` using the
   rubric and record the arithmetic in `score_breakdown` (e.g. `quant3+client2+sector1+sen2+loc1=9`).
3. Deduplicate on employer + role_title + location. If a row already exists, update
   `last_seen` only — do not create a duplicate.
4. Append new rows to `pipeline/tracker.csv` with `status = new`. Set `status = expired` on
   rows whose posting is gone or past deadline. **Never delete a row.**
5. Cross-reference each employer against `config/contacts.md`; put any match in `contact_match`.
6. Commit the updated tracker with message `sweep: YYYY-MM-DD (+N new)`.

**Output to me — this is the only thing I read:**

A single ranked shortlist of at most 25 new postings, highest fit first. For each, exactly:
employer · role · location · fit score · deadline · the one-line reason it scored what it did ·
any visa or language flag · contact match if any · link.

Then three lines: total new found, total filtered out and why (grouped by reason), and
anything expiring within 7 days that I haven't actioned.

## Link verification — every posting, no exceptions

A row whose link does not lead to an actual, live, applicable posting is worse than no row:
it consumes Monday triage attention and, if marked `go`, wastes a whole Thursday draft.
Before a posting is written to the tracker it must pass **all four**:

1. **The link resolves to the posting itself**, not a careers homepage, not a search results
   page, not a redirect to a job-board index. If the URL bounces to a generic landing page,
   the role is filled or withdrawn — set `status = expired` and record
   `notes = dead-link: redirects to <where>`. Do not keep it as `new`.
2. **The posting is still accepting applications.** Reject anything showing "position
   filled", "no longer accepting", "this job was removed", or a passed deadline.
3. **There is a route to apply for THIS role.** A programme or category landing page — a
   "Graduate Programme" overview, a "Careers at X" hub, an office page listing several roles
   — does not count unless you can reach the actual application form for the specific role
   and record that URL. If the application route cannot be found, set
   `status = expired` with `notes = no-application-route: <what the page was>`.
   Record the direct application URL in `source_url`, not the marketing page.
4. **The link works as recorded.** Fetch the exact string you are about to write. Some
   postings 404 without a query parameter (e.g. Prognos needs `?persisted_lang=en`). Save
   the version that actually loads.

Where a page returns 403 or blocks automated fetching, do not guess. Confirm the vacancy
from the employer's own careers page, record that confirmation in `notes`, and only then
keep the row.

## Requirement checks that must happen at sweep time, not at drafting time

These three killed five of seven postings on the 21 September run, and each one was visible
in the posting text. Read the requirements before scoring:

- **Language.** Search the posting for German requirements in both languages: "German",
  "Deutsch", "verhandlungssicher", "fließend", "business level", "advanced", "proficient",
  "very good written and spoken". Any of these at business level or above means
  `status = flagged-language`, per `profile/filters.yaml`. Do not surface it as a normal
  shortlist row. Fluency phrased as "advantageous", "a plus" or "nice to have" is fine —
  set `language_flag = soft_german` and keep the row.
- **Cohort and intake.** Graduate schemes are often restricted to a specific graduating
  cohort ("2027 Bachelor's graduates", "graduating between December 2026 and August 2027",
  "PhD/ABD track"). An MSc completed in 2024 with a year of experience does not qualify for
  a Bachelor's-cohort intake. Score it `seniority_ok = no` and set `status = no` with
  `notes = cohort-mismatch: <the stated cohort>`.
- **Prerequisite experience of a kind I do not have.** Postings demanding prior valuation,
  audit, investment banking or Big-4 experience are not a fit regardless of fit_score on
  other dimensions. Say so in `notes` rather than letting the score carry the row.

## Report the rejections, not just the shortlist

The filtered-out summary must group by reason and name the employer, e.g.
`flagged-language (3): DIW Econ, Guidehouse, Prognos`. Silent filtering hides a
miscalibrated rule — if a whole category is disappearing every week, that is the signal
that the target list or the filters need changing, and it only surfaces if the rejections
are visible.

**Rules:**
- Use named sources. Every posting needs a working link. If you cannot verify a posting is
  live, do not include it.
- Do not write cover letters or CVs in this task.
- Do not email, message or submit anything.
- If a career page is unreachable, note it and move on. Flag pages that fail twice in a row
  so I can remove them from the target list.
- If `filters.yaml` and this prompt ever disagree, `filters.yaml` wins and tell me.

---

## Changelog

| Date | Change | From proposal |
|---|---|---|
| 2026-09-20 | Initial version | — |
