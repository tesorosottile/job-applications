# Monday Triage — 30 minutes

The sweep ran overnight. My job is to turn its shortlist into `go` / `no` decisions and
nothing else. **I do not write anything on Monday. I do not research firms on Monday.**
Drafting is Thursday's job and it only sees rows marked `go`.

---

## Week 1 only: validate before you triage (~20 min)

The first sweep resolved ~80 career-page URLs from a list I assembled from memory. Some are
wrong. Do this once, properly, before trusting a single row.

1. **Open five links at random from the shortlist.** Does each one load, and is it the role
   the row claims? A row whose link 404s or points at a generic careers homepage means the
   sweep is inventing rows from index pages. If two of five fail, stop and fix the prompt
   before triaging anything.
2. **Check the dead-URL report** at the bottom of the run output. Delete those employers from
   `profile/targets.md` now, while it's cheap. Every dead entry costs credits every Monday.
3. **Check three `score_breakdown` cells.** The arithmetic should be visible and should add
   up. `quant3+client2+sector1+sen2+loc1=9` is right. A bare `9` means it's guessing scores
   rather than computing them — that's a prompt bug, fix it before it sets a precedent.
4. **Look at what got filtered out** and why. If it excluded 40 things for `business_german`,
   that's real and expected. If it excluded 40 for `seniority`, my bounds may be too tight.
5. **Sanity-check the count.** Fewer than 5 new postings from ~80 employers means the sweep
   is too narrow or half the URLs are broken. More than 25 means the caps aren't working.

Then prune `targets.md`, commit, and start the triage below.

---

## Every Monday: the triage (~30 min)

### Step 1 — Deadlines first (2 min)
Anything closing within 7 days goes to `go` or `no` immediately, before anything else. A
perfect application submitted after the deadline is worth zero.

### Step 2 — Work top-down, stop at the budget (20 min)

The shortlist is ranked. Start at the top. **Mark at most 6–8 rows `go`.**

That cap is the whole point. Thursday gives me 60 minutes to review drafts properly; 8 drafts
is 7 minutes each, which is already tight. Marking 15 `go` doesn't get me 15 applications, it
gets me 15 drafts I skim and submit badly. Volume comes from doing 8 well every week for 14
weeks, not from one heroic Monday.

If more than 8 look genuinely good: mark the top 8 `go`, leave the rest `new`. They'll still
be there next week and the sweep won't duplicate them.

### Step 3 — The `go` test

Mark `go` only if **all four** are true:

- **I would take this job** if offered on Friday. Not "it's a job" — would I actually go.
- **I clear the bar plausibly.** Not perfectly. If it wants 3 years and I have 2, that's fine.
  If it wants a PhD and 5 years in competition economics, that's not.
- **No blocking flag.** `flagged-language` is a `no` until B2. `flagged-visa` on a UK role is
  only a `go` if fit is 8+, per my own rule — otherwise I'm spending a draft on a lottery.
- **There is something specific to say about this firm.** If I can't name one thing that
  makes it different from the firm above it on the list, the letter will be generic and I'll
  know it when I read it Thursday.

That last test is the one that actually saves time. It catches the applications that would
have been drafted, reviewed, disliked, and submitted anyway.

### Step 4 — Record the `no` reason (5 min)

Every `no` gets a one-word reason in `notes`: `seniority`, `language`, `location`, `domain`,
`wouldnt-take`, `too-senior`, `too-junior`, `no-angle`.

This is not bureaucracy. It's the only input the retro has for calibrating `fit_score`. If I
reject twenty 8s for `wouldnt-take`, the weights are wrong and the sweep is wasting its
effort every week. Without the reasons, the retro can't see that.

### Step 5 — Commit (1 min)

Commit the tracker with `triage: YYYY-MM-DD (N go, M no)`. Thursday's task reads from the
committed file.

---

## Things not to do on Monday

- **Don't research firms.** Thursday's drafting task does that, once, per application.
- **Don't start writing.** Even a good opening line. It breaks the reviewer/author split
  that makes the whole system affordable.
- **Don't mark `go` out of guilt** about a low week. A week with 3 good postings is a week
  with 3 applications. The target is 80 by December, but the target of the *system* is
  interviews, and a padded week produces neither.
- **Don't fix the prompt while triaging.** Note the annoyance in `feedback/` and let the
  retro handle it. Mid-week prompt edits are how the version history becomes useless.

## If the shortlist is consistently thin

Three weeks under 5 new postings means the universe is too small, not that the market is
empty. The fix, in order of cost: add employers to `targets.md`; add aggregators; widen
`seniority.max_years_required`; reconsider whether UK sponsorship roles deserve more weight.
**Do not fix it by lowering the `go` test.**

---

## Changelog

| Date | Change | From proposal |
|---|---|---|
| 2026-09-26 | Initial version | — |
