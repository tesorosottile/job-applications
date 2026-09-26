# Thursday Review — 60 minutes

The drafting task ran overnight on everything I marked `go`. My job is to review, fix,
convert, submit, and spend two minutes writing down what I corrected.

**This is the only hour in the week where the applications actually leave the building.**
Everything else in this system exists to make this hour possible.

---

## Thursday 1 only: test the drafter on two rows (~30 min)

Before trusting a batch of eight, mark only **two** rows `go` and inspect what comes back.
Two is enough to see whether the voice is right; eight bad drafts is not a better test, it's
the same information at four times the cost.

What to check on those two, in this order:

1. **Open `notes.md` first, before the letter.** It lists the evidence IDs used and the
   self-check results. Read it as a claim the system is making about itself.
2. **Then read the letter and verify the claim.** Every factual statement — did it come from
   an evidence ID? Pick the two most impressive-sounding sentences and trace them. If the
   letter says something true-sounding that isn't in `evidence-bank.md`, that is the failure
   mode this whole system is built to prevent, and it means the drafting prompt needs
   tightening before I run a real batch.
3. **Check the self-check honestly.** If `notes.md` ticked "no banned phrase" and the letter
   contains one, the self-check isn't running — it's being asserted. That's worse than having
   no self-check, and it's a fix-now problem.
4. **Count the words.** Over 350 means the cap is being ignored.
5. **Check the firm-specific paragraph cites a real source with a link.** Open the link. If
   the "specific insight about the firm" is invented or generic, the prompt's instruction to
   omit rather than pad isn't landing.

If all five pass on both drafts, scale to 6–8 next week. If any fail, fix the prompt file in
the repo first — that's what the loader indirection is for.

---

## Every Thursday: the review (~60 min)

### Step 0 — Set the budget (1 min)
Count the drafts. Divide 50 minutes by that number. That's the per-draft budget, and it's
usually ~7 minutes. Keep it. The last 10 minutes are for submission admin and feedback.

### Step 1 — Per draft, in this order (~7 min each)

**Read `notes.md` first.** Evidence IDs, self-check, the firm source, the application route,
and anything the letter couldn't fit. 60 seconds.

**Read the cover letter out loud in your head.** The test isn't "is this good writing", it's
**"would I be embarrassed if this person met me and I sounded different?"** Voice drift is
the thing that kills these, and it's only audible when read as speech.

**Scan the CV variant for the re-ordering**, not the content. The content is fixed; what
matters is whether it picked the right variant and led with the right three bullets for this
posting. Wrong variant is a 30-second fix.

**Fix directly.** Don't send it back for a rewrite — that's a round trip you can't afford at
7 minutes a draft. Edit the text yourself, in the file.

### Step 2 — Red flags that mean "don't submit this one"

- A claim I can't trace to an evidence ID
- A sentence I wouldn't say out loud
- The firm paragraph could be swapped to any other firm on the list unchanged
- It leads with gaming or marketing
- It's apologetic about the one year of experience rather than matter-of-fact about it

A draft with any of these goes back to `status = go` and gets redone next week, or gets
dropped. **Submitting something I don't stand behind is worse than not applying** — these
firms are small, people move between them, and a weak application is remembered.

### Step 3 — Convert and submit (~10 min total)

The drafts are markdown. Firms want PDF. Two routes:

- **Ask a Cowork session**: "convert the .md files in `applications/<folder>/` to PDF using
  a clean single-column layout, same filenames." Cheap, and it handles the batch at once.
- **Locally with pandoc**: `pandoc cv.md -o cv.pdf` — faster, no credits, but you need
  pandoc and a LaTeX engine installed.

Name the files the way a recruiter will read them in a folder of 300:
`Sottile_CV_<Firm>.pdf`, `Sottile_CoverLetter_<Firm>.pdf`.

Then submit through whatever route `notes.md` identified. **Keep the portal confirmation
email** — some firms' only proof you applied.

### Step 4 — Update the tracker (~3 min)

`status = submitted`, fill `applied_date`, clear `next_action`. Commit.

### Step 5 — Write `feedback/YYYY-MM-DD.md` (~2 min)

**Do not skip this.** It is the entire input to the monthly retro, and it is the difference
between a system that gets better and one that repeats the same mistake for fourteen weeks.

Write the *rule behind the correction*, not the corrected text:

- ✅ "Cut the opener on the Frontier letter — it restated the job title back at them. Third
  time. The prompt should forbid it."
- ❌ "Fixed the Frontier opener."

The second tells the retro nothing. Also record anything that passed a self-check it
shouldn't have — that's the highest-value entry in the folder.

---

## Things not to do on Thursday

- **Don't research firms yourself.** If the draft's firm paragraph is thin, either the source
  wasn't there or the prompt is weak. Note it in feedback; don't compensate by hand, or
  you'll be doing it every week forever.
- **Don't rewrite from scratch.** If a draft needs a full rewrite, the input was wrong —
  wrong variant, wrong evidence, bad posting. Fix the input, not the output.
- **Don't let the batch grow past 8.** If Monday gave you 12 `go` rows, do 8 and leave 4 for
  next week. A 90-minute Thursday happens once, then it stops happening at all.
- **Don't edit prompt files mid-review.** Note it, let the retro propose it.

## If drafts are consistently good

Raise the batch to 10 and see if quality holds. The cap is a guess about your review speed,
not a law. But raise it from evidence — three clean weeks — not from optimism in week two.

---

## Changelog

| Date | Change | From proposal |
|---|---|---|
| 2026-09-26 | Initial version | — |
