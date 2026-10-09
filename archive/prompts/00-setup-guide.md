# Setting Up the Scheduled Tasks

Do this after the repo is pushed and cloned. Roughly 45 minutes including the test runs.

---

## Step 0 — Connect GitHub

Scheduled tasks run **remotely** — on their cadence, even when your laptop is asleep and the
desktop app is closed. That only works if the files they need live somewhere remote-reachable.
This is the whole reason the system is on GitHub rather than in a local folder: a task scoped
to a local directory requires your machine to be awake and Claude Desktop running, which
defeats the point.

1. In Claude: **Customize → Connectors → Add**, then connect GitHub and authorise access to
   the private `tesorosottile/jobsearch` repo (grant it to that repo only, not all repos).
2. Still under Connectors, open **Tool permissions** for GitHub. Set read and file-write tools
   to *Always allow*; leave anything destructive on *Needs approval*. This is what keeps an
   unattended run from doing something you'd have to undo.
3. Connectors are account-level and shared between Claude and Cowork — connecting GitHub here
   also makes it available to your other project, and vice versa. Nothing is "used up."

## Step 1 — Create the sourcing sweep

1. Open **Cowork**, click **+ New task**.
2. Paste the entire contents of `prompts/01-sourcing-sweep.md` as the prompt.
3. Before scheduling, **run it once manually** and read the output properly. Expect the first
   run to be slow — it's resolving ~80 career page URLs from scratch — and expect several
   dead entries. Prune them from `profile/targets.md` before you schedule anything.
4. Once the output looks right: type `/schedule` in that task, or click **Schedule this task**.
5. Cadence **Weekly, Monday, 06:00**. Note that execution time varies with demand, so don't
   build your morning around an exact minute.
6. Approval mode: automatic. It only reads the web and writes to the repo.

## Step 2 — Create the batch drafting task

1. New task, paste `prompts/02-batch-drafting.md`.
2. Before the first real run, mark **two** tracker rows as `status = go` by hand and run it.
   Two is enough to see whether the voice is right; eight wasted drafts are not a better test.
3. Read the generated `notes.md` files as carefully as the letters — that's where you find out
   whether it's inventing claims or padding the firm paragraph.
4. Schedule **Weekly, Thursday, 06:00**.
5. Approval mode: automatic. It writes files and never submits anything.

## Step 3 — Create the pipeline digest

1. New task, paste `prompts/03-pipeline-digest.md`.
2. Schedule **Weekly, Sunday, 18:00**. Read-only, cheap, no test run needed.

## Step 4 — Manage them

All three appear under **Scheduled** in the sidebar. From there you can edit a prompt, change
cadence, pause, or review past runs. Check past runs every few weeks — quality drifts, and a
scheduled task failing quietly is worse than one that never ran.

---

## Prompt hygiene that matters for these three

- **Named sources and exact date ranges.** "Last 14 days" beats "recently"; the filter file
  carries the number so the prompt doesn't have to.
- **Say where output goes.** Each prompt states which file it writes and what it reports back.
- **Require links** for anything factual. A posting with no verifiable link doesn't exist.
- **Narrow scope.** Broad scheduled tasks run long and burn credits. That's why sourcing,
  drafting and reporting are three tasks rather than one.
- **Approval steps before anything irreversible.** None of these three send, submit, publish
  or delete — by design. You are the only thing that submits an application.

## If credits run tight

Duplicate the sourcing task, cut `profile/targets.md` down to the top 25 firms in the copy, and
alternate: full sweep one week, narrow sweep the next. The digest costs almost nothing.
Drafting scales with how many rows you mark `go`, so that's your real throttle — not a setting.

## First four weeks — what to actually watch

| Week | Watch for |
|---|---|
| 1 | Dead URLs, firms with no relevant openings ever. Prune the target list hard. |
| 2 | Is `fit_score` ranking things the way you'd rank them? If not, change the weights in `filters.yaml`. |
| 3 | Are the letters distinguishable from each other? If two read the same, the evidence selection is too narrow. |
| 4 | Volume check against 80 by 31 December. If you're behind, the fix is widening `targets.md`, not lowering the bar. |
