# Sunday Digest — 15 minutes

The cheapest and most skippable ritual in the system, which is exactly why it needs to be
written down. Its job is to stop applications dying of silence.

Most rejections are never sent. A firm that liked your application but got distracted looks
identical, from your side, to a firm that binned it. The follow-up is what separates them.

---

## Sunday 1 only (~5 min)

There's almost nothing in the tracker yet, so just check the digest can read the file and
that its arithmetic is right. If it reports counts that don't match what you know you did
this week, the digest prompt has a bug — fix it now while the tracker is small enough to
verify by eye.

---

## Every Sunday: the digest (~15 min)

### Step 1 — Read the five sections (3 min)

Due this week · Drafted not submitted · Gone quiet · Numbers · One thing.

If a section says "nothing", move on. The digest is under 300 words by design.

### Step 2 — Rescue anything drafted but not submitted (2 min)

A draft sitting unsubmitted for 5+ days is the most wasteful state in the system — the credits
are spent, the work exists, and it's producing nothing. Either submit it now, or mark it `no`
and record why. **Don't let it sit a third week.** If this happens repeatedly, Thursday's
batch is too big.

### Step 3 — Send follow-ups (7 min)

For anything applied 10+ days ago with no response. One short email to whoever is named on the
posting, or the generic recruiting address.

Keep it to three sentences. The goal is to be a name they've now seen twice, not to make an
argument:

> Subject: Application — <Role>, <your name>
>
> Hi <name>,
>
> I applied for the <role> position on <date> and wanted to check the search is still
> active. Happy to send anything else that would be useful — I'm particularly interested in
> <the one specific thing from the firm paragraph>.
>
> Best,
> Gianluigi

**Once only.** A second follow-up on the same application reads as desperate and it's the
only part of this system that can actively damage you. After one unanswered follow-up, mark
`status = no-response` and move on.

Update `last_contact` on every row you touch.

### Step 4 — Record responses (2 min)

Anything that came back this week: `responded`, `interview`, or `rejected`. Rejections matter
as much as interviews — they're the denominator, and without them the retro's response-rate
number is meaningless.

If a rejection says anything specific about why, put it in `notes`. Three rejections citing
the same gap is the most useful signal you will get all autumn, and it's the one thing the
tracker can surface that no amount of prompt tuning can.

### Step 5 — Pace check (1 min)

The digest compares cumulative submissions against 80 by 31 December. If you're behind:

The fix is **widening the funnel, never lowering the bar**. More employers in `targets.md`,
more aggregators, looser `max_years_required`. Padding a week with applications you don't
want produces neither interviews nor a usable signal.

And if you're behind by a lot in November — say under 45 — that's worth knowing *before* the
December conversation, not after. It changes what leverage you actually have, and it's better
to walk into that meeting with an honest read than an optimistic one.

---

## First Sunday of the month: the retro (+15 min)

The retro task writes `proposals/YYYY-MM-DD.md`. Read the file, not its summary.

Review each proposal in this order:

1. **Does it touch a FROZEN path?** → reject, and note that the retro is drifting. Two of
   these in a row and pause the retro task entirely.
2. **Is the evidence at least 3 cited instances?** → if not, reject. One annoyance repeated
   back to me with confidence is not a finding.
3. **Is it encoding something I actually corrected repeatedly**, or is it the system tidying
   itself? Only the former is worth merging.
4. **What does it cost if it's wrong?** The retro must have answered this. Weight "letters
   get quietly worse in a way I won't notice" very heavily.

**Then apply the edit myself** and log it in the changelog of the file I edited. The retro
never edits the target file — that separation is the whole safeguard.

Keep rejected proposals. A retro proposing the same rejected thing three times is telling me
something, either about the retro or about a real problem I keep declining to fix.

**A retro that proposes nothing is a good retro.** Don't merge something to justify the run.

---

## Things not to do on Sunday

- **Don't send a second follow-up.** Ever.
- **Don't triage new postings.** That's Monday. The digest is read-only for a reason.
- **Don't do a "quick" extra application** because the week felt thin. Unreviewed submissions
  are how the quality bar quietly disappears.

---

## Changelog

| Date | Change | From proposal |
|---|---|---|
| 2026-09-26 | Initial version | — |
