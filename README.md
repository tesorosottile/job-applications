# Job Search System

> ⚠️ **KEEP THIS REPOSITORY PRIVATE.** It contains personal contact details, full employment
> history, notes on employers, and eventually names of people in my network.

Target: ~80 applications submitted by 31 December 2026, at ~2 hours of my time per week.
Contract at rcp expires 1 February 2027; the December negotiation is the forcing function.

## Structure

```
profile/     cv-master.md, cv-variants/, evidence-bank.md, narratives.md, voice.md
config/      filters.yaml (the rules), targets.md, contacts.md
pipeline/    tracker.csv — system of record, one row per posting
prompts/     the three scheduled-task prompts
applications/  one folder per application, generated
```

## The rule that makes this work

**I am the reviewer, not the author.** Anything that can be selected from the evidence bank
should never be written from scratch. Any claim not traceable to an evidence ID is a
hallucination and gets rejected.

## Setup order

1. Create the private repo under `tesorosottile`, push these files, clone via GitHub Desktop.
2. Connect GitHub in Claude → Customize → Connectors. Set tool permissions: writes to this
   repo allowed, everything else needs approval.
3. Fill `config/contacts.md` (~30 min, once).
4. Review `config/targets.md` and veto anything you'd never actually join.
5. Create the three scheduled tasks in Cowork (`/schedule` or the Scheduled tab), pasting each
   prompt from `prompts/`. **Run each once manually and inspect the output before trusting the
   cadence.**
6. Build `cv-variants/` from `cv-master.md` — four variants, done once, by hand or in a
   session with Claude. Everything downstream depends on these being right.

## Weekly rhythm (~1h 45m)

| When | What | Me |
|---|---|---|
| Mon 06:00 | Sourcing sweep runs | 30 min: triage shortlist to `go` / `no` |
| Thu 06:00 | Batch drafting runs | 60 min: review 6–8 drafts, submit |
| Sun 18:00 | Pipeline digest runs | 15 min: read, send follow-ups |

## Status values in tracker.csv

`new` → `go` / `no` → `drafted` → `submitted` → `responded` / `interview` / `rejected`
Plus: `expired`, `flagged-language`, `flagged-visa`.

## Credit management

The sweep is the expensive task. If credits run tight: alternate a full sweep one week with a
top-25-firms-only sweep the next. The digest is near-free. Drafting scales with how many rows
you mark `go` — that's your real throttle.

## Change log for rules

Change filters in `config/filters.yaml`, never in a prompt. When German reaches B2, change
`business_german_required: exclude` to `include` — one line, and every future run inherits it.
