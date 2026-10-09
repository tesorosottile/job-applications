# Handoff — GitHub connector work on `tesorosottile/job-applications`

Paste everything below the line into a session that has the GitHub connector's tools loaded.
Check first that they actually are: the connector being authorised in settings is not the
same as its tools being enabled in the chat. If no GitHub tool is callable, say so and stop —
do not fall back to guessing.

---

## Context

Gianluigi Sottile is running a job search out of a private GitHub repo,
**`tesorosottile/job-applications`**. Four Cowork scheduled tasks read their instructions
from that repo and write results back to it. His contract ends 1 February 2027 and he has
about two hours a week for this, so the system exists to make him a *reviewer* rather than an
author.

The repo is cloned on his Windows laptop at `C:\Users\acer\Documents\GitHub\job-applications`
and the scheduled tasks reach it as a connected folder.

## The immediate job

**Three commits exist on the laptop clone that have never reached GitHub.** Every attempt to
push from an agent shell failed with `HTTP code 403 from proxy after CONNECT` — GitHub is
outside the egress allowlist for that sandbox. The commits are good; only the transport
failed.

- Remote `origin/main` is at **`865595f`** ("Add files via upload")
- Local `main` is at **`fe39632`**, three ahead:
  1. `5b3800e` — operating guides, prompt policy, loader indirection, retro task
  2. `f6e7ac6` — `tools/triage.html`
  3. `fe39632` — caught-up Thursday run, hardened sweep prompt

**Preferred fix, and by far the simplest: ask him to click Push in GitHub Desktop.** It is
already open on his machine and it has working credentials. Do that before anything clever.

Only if he cannot: reconstruct the three commits through the connector by writing the
changed files to `main`. Files changed across the three commits:

```
README.md                      PROMPT-POLICY.md
MONDAY-TRIAGE.md               THURSDAY-REVIEW.md          SUNDAY-DIGEST.md
.gitattributes
prompts/00-setup-guide.md      prompts/LOADERS.md          prompts/04-retro.md
prompts/01-sourcing-sweep.md   prompts/02-batch-drafting.md
prompts/03-pipeline-digest.md
pipeline/tracker.csv
tools/triage.html
feedback/README.md             feedback/2026-09-27.md
proposals/README.md
applications/rbb-economics-associate/{cv,cover-letter,notes}.md
```

Read each from the laptop clone and write it to the repo unchanged. **If you reconstruct
rather than push, tell him the local clone is then ahead-and-diverged and he must reconcile
it** (easiest: `git fetch && git reset --hard origin/main` once he has confirmed nothing
local is unsaved). Leaving that unsaid will cost him an afternoon later.

## Hard constraints — read `PROMPT-POLICY.md` in the repo before editing anything

- **`profile/voice.md` and the Rules sections of every file in `prompts/` are FROZEN.** Do
  not edit them, do not "improve" them, do not let a scheduled task edit them. They are the
  constraints on generated output; an agent that can edit its own constraints will eventually
  edit away whichever one blocks it most often.
- **The most protected line in the repo:** every factual claim in a generated CV or cover
  letter must trace to an ID in `profile/evidence-bank.md`. No inference, no synthesis, no
  "reasonable extrapolation from the CV". A claim without an ID is a hallucination.
- **The monthly retro writes to `proposals/` only.** It proposes; he merges by hand. Nothing
  self-applies.
- **`.gitattributes` sets `* text=auto eol=lf`.** It was added because the whole repo was
  showing as modified on every diff from CRLF churn, which destroys the version history the
  system depends on. Do not remove it, and do not commit a CRLF renormalisation on top of it.
- **Never Excel on `pipeline/tracker.csv`.** It reformats dates into a local format the tasks
  cannot parse and mangles UTF-8 in employer names (`Öko-Institut`).

## State as of 2026-09-27

`pipeline/tracker.csv` has 7 rows, all verified against the live postings that morning:

| Status | Rows |
|---|---|
| `drafted` | RBB Economics — Associate. Files in `applications/rbb-economics-associate/`, ready for him to review and submit |
| `flagged-language` | DIW Econ, Guidehouse, Prognos, Alvarez & Marsal — all require business-level German, excluded by `profile/filters.yaml` |
| `expired` | McKinsey — URL redirects to a careers homepage; role filled |
| `no` | CRA — posting is for BSc graduating Dec 2026–Aug 2027; wrong cohort for a 2024 MSc |

Scheduled tasks, all enabled, all with the repo root attached as a folder:

| Task | Cron (UTC) | Local |
|---|---|---|
| Sourcing sweep | `0 4 * * 1` | Mon 06:00 |
| Batch drafting | `0 4 * * 4` | Thu 06:00 |
| Pipeline digest | `0 16 * * 0` | Sun 18:00 |
| Monthly retro | `0 17 1 * *` | 1st of month, 19:00 |

Two older triggers are disabled and prefixed `[SUPERSEDED]`. He can delete them once he has
seen the replacements run.

Note: Europe/Rome leaves DST on 25 October 2026, after which each of these fires an hour
earlier in local time. Harmless for the 06:00 tasks; worth a look for the 18:00 digest.

## The open question, which matters more than the push

Four of the seven postings died on the German requirement, and that will repeat most weeks,
because his target list is mostly German while his German is B1. The pipeline will not reach
80 applications by December against a universe that is structurally closed to him.

`feedback/2026-09-27.md` sets out three responses: reweight `profile/targets.md` towards
English-working offices (UK, Brussels, EU institutions — RBB is the model, one general
application across all offices), promote UK sponsorship roles from long shot to main line,
and treat B2 German as a dated goal rather than an intention, because Guidehouse is the best
domain fit seen so far and only the language line blocks it.

**Do not act on this unilaterally.** `profile/targets.md` and `profile/filters.yaml` are
PROPOSABLE, not FREE — he decides. Raise it, show him the evidence, let him choose.

## Traps that have already cost time

1. **Agent shells cannot reach github.com** (403 at the proxy). Do not retry a push from one;
   route it through the connector or through him.
2. **Git in the connected folder cannot delete its own lock files** — `rm` fails with
   "Operation not permitted" until deletion is granted for that folder. A leftover
   `.git/index.lock` blocks GitHub Desktop entirely. After any git operation from a shell,
   check `find .git -name "*.lock"` and clean up.
3. **A scheduled task's connected folders are fixed at creation.** They cannot be added by
   editing the prompt. The original sweep task ran for a week with no folder attached, did
   the research, and had nowhere to write it — which is why the tracker sat empty. If a task
   needs a different folder, recreate it.
4. **Verify every posting link before drafting.** Three failure modes have already been seen:
   a URL redirecting to a careers homepage, a programme landing page with no application
   route, and a posting that 404s without a query parameter. The rules are now in
   `prompts/01-sourcing-sweep.md`.
5. **All four tasks depend on his laptop being awake** with the desktop app running, because
   they reach the repo as a local folder. Moving them to the GitHub connector would remove
   that dependency — probably the single highest-value change available, and worth proposing
   once the push is sorted.
