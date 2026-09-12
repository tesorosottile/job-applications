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

**Rules:**
- Use named sources. Every posting needs a working link. If you cannot verify a posting is
  live, do not include it.
- Do not write cover letters or CVs in this task.
- Do not email, message or submit anything.
- If a career page is unreachable, note it and move on. Flag pages that fail twice in a row
  so I can remove them from the target list.
- If `filters.yaml` and this prompt ever disagree, `filters.yaml` wins and tell me.
