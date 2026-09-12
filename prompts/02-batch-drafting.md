# Scheduled Task 2 — Batch Drafting

**Cadence:** Weekly, Thursday 06:00
**Approval mode:** auto (writes files only — never submits)
**Paste everything below as the task prompt.**

---

You are drafting job applications for Gianluigi Sottile.

**Read first:**
1. `profile/voice.md` — binding on every word you write.
2. `profile/evidence-bank.md` — the only permitted source of factual claims.
3. `profile/narratives.md` — the reusable answers.
4. `profile/cv-master.md` and `profile/cv-variants/`.
5. `pipeline/tracker.csv` — work only on rows where `status = go`.

**For each `status = go` row:**

1. Create `applications/<employer-slug>-<role-slug>/`.
2. Write `cv.md` — start from the closest variant, re-order and trim to the posting. You may
   cut and re-phrase. You may NOT add any claim not in the evidence bank.
3. Write `cover-letter.md` — max 350 words, structured as:
   - Opening: the specific thing about this role or firm, grounded in a real named source.
   - Body: two evidence items, chosen for this posting, with numbers.
   - The relevant narrative from N1/N2/N4, adapted not pasted.
   - Close: short. No restating the application.
4. Write `notes.md` containing:
   - Evidence IDs used, listed.
   - The voice.md self-check, each box ticked or explained.
   - The source you used for the firm-specific paragraph, with link.
   - Anything in the posting I should address that the letter couldn't fit.
   - Application route (portal / email / form) and anything it will ask for.
5. Update the row: `status = drafted`, `next_action = review and submit`.

**Rules:**
- If you cannot find a real, specific, citable fact about the firm, write the letter without
  a firm-specific paragraph and say so in notes.md. Do not invent enthusiasm.
- If a posting requires business German, stop and set `status = flagged-language`.
- Never submit, never email, never fill a form. You produce files; I submit.
- Batch everything into this one session rather than one run per application.

**Output to me:** one line per application — folder path, word count, evidence IDs used, and
any flag. Then list anything you could not draft and why.
