# Prompt Policy

Governs how the instructions in this repo may change. Every scheduled task reads this file
before acting. **I am the only one who merges.**

---

## The three tiers

### FROZEN — never changed by any automated process

These exist to constrain output. An agent that can edit them can edit away the reason it
exists. Only I change these, by hand, in a session where I am present.

- `profile/voice.md` — **all of it**, especially the hard rules and the banned-phrase list
- The "Rules" section of every file in `prompts/`
- `PROMPT-POLICY.md` — this file
- Rule 1 of voice.md (every claim traces to an evidence ID) is the single most protected
  line in this repository. It is the thing standing between me and a letter that confidently
  claims I led a team of six.

### PROPOSABLE — the retro may propose changes; I merge or reject

- The "Do" steps in `prompts/01`, `02`, `03`
- Output formats and what gets reported back to me
- `profile/filters.yaml` — scoring weights, geography rules, seniority bounds
- `profile/targets.md` — adding or removing employers
- `profile/evidence-bank.md` — **additions only**, never edits to existing entries
- `profile/narratives.md` — proposals must show the diff; N3 template shape is frozen

### FREE — the tasks write these as normal operation

- `pipeline/tracker.csv`
- `applications/**`
- `profile/targets-resolved.yaml`
- `proposals/**`

---

## How a change happens

1. The retro writes `proposals/YYYY-MM-DD.md`. It commits **only to that path**.
2. I read it. It must contain, per proposal: the exact file and line, the proposed new text,
   the evidence from the last month's runs that motivated it, and what it costs me if the
   change is wrong.
3. I edit the file myself, or tell a live session to. **The retro never edits the target.**
4. I log the change in the changelog at the bottom of the file I edited.

## Rejection is the default

A retro that proposes nothing is a good retro. A retro that proposes six changes a month is
overfitting to noise and should be made less frequent, not obeyed.

## Things the retro may never propose

- Relaxing or removing the evidence-ID requirement, in any form, including "allow reasonable
  inference from the CV" or "permit synthesis across entries"
- Raising the 350-word cap
- Removing the banned-phrase list or any entry in it
- Removing the requirement that firm-specific paragraphs cite a named source
- Granting itself, or any task, write access to FROZEN paths
- Adding a step that submits, sends, emails or publishes anything

If a proposal touches any of the above, I reject it without reading further and note that the
retro is drifting. Two such proposals in a row and I pause the retro task entirely.

## The honest caveat about all of this

The feedback I give after a Thursday review tells me whether a letter *reads* well. Whether it
*worked* arrives weeks later as an interview invitation, filtered through firm-specific noise
I cannot see. With ~80 applications and a response rate somewhere in the 5–15% band, I will
never have the statistics to attribute an outcome to a prompt change.

So this loop is **craft refinement with a memory**, not optimisation. Its real value is that
a correction I make in October is still in force in December, instead of being re-explained
in every session. That alone justifies it. Anything more is a story I would be telling myself.

## Retro cadence review

If after three retros the proposals are mostly cosmetic, move the retro to quarterly. The
cost of running it is small; the cost of acting on noise is not.
