# Loader Prompts

**These short texts go into the Cowork scheduled-task config. The real instructions stay in
the repo.** A prompt change is then a commit — with history, diffs and rollback — rather than
a fiddle in a settings panel.

## How the tasks reach the repo

The repo lives on my computer at `C:\Users\acer\Documents\GitHub\job-applications`, attached
to each task as a **connected folder**. In the device shell it is at
`$HOME/mnt/job-applications`.

**This means the tasks need my laptop awake and the desktop app running.** Scheduled tasks
normally run remotely regardless of my machine, but these depend on local folders, so a
closed laptop on Monday morning means no sweep. See "Known fragility" below.

---

## Task 1 — Sourcing Sweep (Weekly, Monday 06:00 local)

```
You are running the weekly job sourcing sweep for Gianluigi Sottile. Fresh session,
no memory of previous runs — all context comes from the repo.

The repo is the connected folder "job-applications"
(C:\Users\acer\Documents\GitHub\job-applications, at $HOME/mnt/job-applications in
the device shell). Read prompts/01-sourcing-sweep.md there and follow it exactly.
That file is authoritative; if anything here conflicts with it, that file wins.

Read PROMPT-POLICY.md before acting. Do not modify anything in prompts/ or
profile/voice.md during this run.

If the repo folder is not reachable after one retry, STOP and say so plainly. Do not
run the sweep from memory, and do not claim the tracker was updated when it was not.
```

## Task 2 — Batch Drafting (Weekly, Thursday 06:00 local)

```
You are drafting job applications for Gianluigi Sottile.

The repo is the connected folder "job-applications"
(C:\Users\acer\Documents\GitHub\job-applications, at $HOME/mnt/job-applications in
the device shell). Read prompts/02-batch-drafting.md there and follow it exactly.
That file is authoritative.

Read PROMPT-POLICY.md before acting. Do not modify anything in prompts/ or
profile/voice.md during this run.

If the repo folder is not reachable after one retry, STOP and say so. Never draft
from memory — every factual claim must come from profile/evidence-bank.md as it
exists in the repo right now.
```

## Task 3 — Pipeline Digest (Weekly, Sunday 18:00 local)

```
Read prompts/03-pipeline-digest.md in the connected folder "job-applications"
(C:\Users\acer\Documents\GitHub\job-applications, at $HOME/mnt/job-applications)
and follow it exactly. Read-only: write nothing, commit nothing, research nothing.

If the repo folder is not reachable, say so plainly rather than reporting from memory.
```

## Task 4 — Monthly Retro (Monthly, first Sunday 19:00 local)

```
Read prompts/04-retro.md in the connected folder "job-applications"
(C:\Users\acer\Documents\GitHub\job-applications, at $HOME/mnt/job-applications)
and follow it exactly. Read PROMPT-POLICY.md first — it governs what you may and
may not propose changing.

You may write only to proposals/. You may not modify prompts/, profile/ or
pipeline/ directly under any circumstances.

If the repo folder is not reachable, stop and say so.
```

---

## Why the "stop, don't improvise" line is in every one

Without it, a task that cannot reach the repo will cheerfully run from whatever it
half-remembers and write plausible-looking fiction into the tracker. Loud failure is much
cheaper than quiet fabrication. This has already happened once: the 21 September sweep ran
without folder access, so its shortlist never reached `tracker.csv`.

## Known fragility

Because the repo is reached as a local folder rather than through the GitHub connector,
**every task depends on the laptop being awake and the desktop app running at the scheduled
time.** Two consequences:

1. A closed laptop means a silently skipped week. Check the Scheduled tab's run history every
   couple of weeks rather than assuming the runs happened.
2. A task's connected folders are fixed when it is created and cannot be added later by
   editing the prompt — a task without the folder attached can read nothing, and has to be
   recreated to fix it.

**The robust fix** is adding the GitHub connector so tasks reach the repo from the cloud,
independent of the laptop. Worth doing before November, when a missed week starts to cost
real pipeline.

## One caveat on indirection

You can no longer tell what a task did by reading its config — you have to check which commit
of the prompt file was live at the time. That is what the changelog at the bottom of each
prompt file is for. Keep it updated or the version history stops being useful.
