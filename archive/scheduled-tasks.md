# v1 scheduled tasks (retired 2026-10-09)

All four were **disabled and renamed `[ARCHIVED] …`** on 2026-10-09, not deleted, so their run
history survives. Each had this repo attached as a local connected folder, which is why they
needed the laptop awake. Delete them once the v2 Monday sweep has run successfully once.

| ID | Name | Cron (UTC) | Read |
|---|---|---|---|
| `trig_01HW85UCuaWTqSYeoTy1nS63` | Job search — sourcing sweep (Mon) | `0 4 * * 1` | `prompts/01-sourcing-sweep.md` |
| `trig_01NqDjVMQ6eJ8rBi42HhVLSV` | Job applications — batch drafting (weekly) | `0 4 * * 4` | `prompts/02-batch-drafting.md` |
| `trig_01RhzTEaKi7gJAg1KeJ8ijNm` | Job search — pipeline digest (Sun) | `0 16 * * 0` | `prompts/03-pipeline-digest.md` |
| `trig_01L72mEBP2tA6HdUUERvsSzY` | Job search — monthly retro | `0 17 1 * *` | `prompts/04-retro.md` |

Each task's prompt was a short loader: "Read `prompts/<file>` in the connected folder
`job-applications` and follow it exactly; read `PROMPT-POLICY.md` first; if the folder is not
reachable, stop and say so." The real instructions are in `archive/prompts/`.

Last recorded runs: sweep and digest 2026-09-28 (succeeded); drafting 2026-09-26 (succeeded).
