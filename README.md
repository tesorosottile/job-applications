# Job Search System

> ⚠️ **KEEP THIS REPOSITORY PRIVATE.** It contains personal contact details, full employment
> history, notes on employers, and names of people in my network.

Target: ~80 applications submitted by 31 December 2026, at ~2 hours of my time per week.
Contract at rcp expires 1 February 2027; the December negotiation is the forcing function.

---

## Summary — how this works

Four scheduled tasks do the work I can't afford to do by hand. I am the reviewer, not the
author.

**The week:**

| When | The task does | I do | Guide |
|---|---|---|---|
| **Mon 06:00** | Sweeps ~80 employers, scores and ranks new postings into the tracker | 30 min: mark rows `go` / `no` | `MONDAY-TRIAGE.md` |
| **Thu 06:00** | Drafts CV + letter for every `go` row | 60 min: review, convert to PDF, submit, write feedback | `THURSDAY-REVIEW.md` |
| **Sun 18:00** | Digests the pipeline: due, stale, silent, pace | 15 min: send follow-ups, record responses | `SUNDAY-DIGEST.md` |
| **1st Sun/mo** | Reads a month of runs and my feedback, writes change proposals | +15 min: merge or reject | `SUNDAY-DIGEST.md` |

**The two rules everything rests on:**

1. **Every factual claim in a generated document traces to an ID in
   `profile/evidence-bank.md`.** No exceptions. A claim without an ID is a hallucination and
   the draft gets rejected. This is the most protected rule in the repo.
2. **Nothing self-applies.** The retro writes proposals; I merge them by hand.
   `PROMPT-POLICY.md` marks `voice.md` and every prompt's Rules section as frozen, because an
   agent that can edit its own constraints eventually edits away whichever one blocks it most.

**Where the leverage is:** the evidence bank and narrative library mean drafting is
*selection*, not generation — cheaper in credits, more consistent in voice, and far less
prone to invention. The cap of 6–8 drafts a week is set by my review capacity, not by
ambition; 80 applications comes from doing 8 well for fourteen weeks.

---

## Structure

```
README.md            this file
PROMPT-POLICY.md     what may change, what is frozen, who merges — read before editing prompts
MONDAY-TRIAGE.md     Monday: shortlist → go/no — 30 min
THURSDAY-REVIEW.md   Thursday: review, convert, submit, write feedback — 60 min
SUNDAY-DIGEST.md     Sunday: follow-ups, responses, pace — 15 min (+15 monthly retro)

profile/     cv-master.md, cv-variants/, evidence-bank.md, narratives.md, voice.md,
             filters.yaml (the rules engine), targets.md, contacts.md, targets-resolved.yaml
pipeline/    tracker.csv — system of record, one row per posting
prompts/     LOADERS.md (what goes in the task config) + the four task prompts
feedback/    my session notes — the only input to the monthly retro
proposals/   retro output. I merge by hand. Nothing self-applies.
applications/  one folder per application, generated
```

## How the tasks reach the repo

Each scheduled task has this repo attached as a **connected folder**
(`C:\Users\acer\Documents\GitHub\job-applications`). The task config holds only a short
**loader** (`prompts/LOADERS.md`) pointing at the real prompt file here — so changing
behaviour is a commit, not a settings edit.

**Consequence worth knowing:** these tasks need the laptop awake and the desktop app running.
A closed laptop on Monday means a silently skipped week. Adding the GitHub connector would
remove that dependency — worth doing before November.

## Marking rows

Edit the `status` column in `pipeline/tracker.csv` via the github.com web editor or a
plain-text editor. **Never Excel** — it reformats dates into a local format the tasks can't
parse and mangles UTF-8 in employer names (`Öko-Institut`).

`new` → `go` / `no` → `drafted` → `submitted` → `responded` / `interview` / `rejected`
Plus: `expired`, `flagged-language`, `flagged-visa`, `no-response`.

## Credit management

The sweep is the expensive task. If credits run tight, alternate a full sweep one week with a
top-25-firms-only sweep the next. The digest is near-free. Drafting scales with how many rows
I mark `go` — that's the real throttle, and it's a decision, not a setting.

## Changing the rules

Change filters in `profile/filters.yaml`, never in a prompt. When German reaches B2, change
`business_german_required: exclude` to `include` — one line, and every future run inherits it.
