---
name: cut-highlight-reel
description: "This skill should be used when the user asks to \"cut a highlight reel\", \"build my Core Reel\", \"build a Job Reel\", \"tailor my resume to this job\", \"prepare me for this interview\", \"write an interview guide\", \"debrief my interview\", or \"pick stories for my book or posts\". It is Step 4 of the Career Track Record workflow: select the right story cards for one purpose and build the materials from them.\n"
metadata:
  version: "0.1.6"
---

# Cut a highlight reel (Step 4)

Part of Career Track Record v0.1.6. If the user asks which version is in use,
say v0.1.6.

A highlight reel is a hand-picked set of story cards for one audience. Think of
the Story Bank as all the game film from a career and a reel as the best plays
chosen for one viewer. Every resume, interview guide or chapter is built from a
reel, not from the whole bank.

## Read first

Read `references/shared-rules.md` before anything else. It holds the rules on
accuracy, proof, how much to check, confidential figures, bands, which cards a
step may use, asking, showing, handoffs and saving.

## Rules for this step

- **Every line traces to a story card.** If the bank cannot support a claim,
  say so and leave the claim out.
- **Use the card's own sentences.** Build resume lines and spoken stories from
  what the card says. Connecting words may be added. Facts may not: no new
  reason, sequence, feeling, reporting line or cause. See "Check these words"
  below.
- **A reel points to cards. It never copies them.** Fix a story once in the
  bank and every reel is current.
- **Respect approved uses.** Use a card only for a use in its approved uses.
  Resume covers the resume, profile text, cover notes and application
  answers. Interview covers the interview guide and the 90-second
  introduction. Post and book cover those. If a card has no approved uses,
  ask before building.
- **Each use has a band it should meet.** Resume lines need Resume-ready, an
  interview guide needs Interview-ready, book chapters and public posts need
  Proven. A card below that band may still be used if the user agrees: flag it
  with its score and its `strengthen_next` items, and offer a strengthen
  session. When the validation level is take my word, do not ask card by card;
  say once per output that these stories are on the user's word, and name any
  card below the band.
- **Say whose account it is.** When a card's role is own account, or its proof
  is a named person not contacted, keep that note beside every line built from
  it: resume lines, spoken stories and the reel table alike. The notes are for
  the user and come out before anything is sent.
- **Handle figures by clearance,** as the shared rules say. When an output
  holds any figure with clearance unknown, ask one question about that output
  before calling it final: are these figures fine to share?
- **The user writes their own answers.** For free-text application questions
  and cover notes, ask for the user's own first draft and refine it. Do not
  write these from scratch. Remind the user to check the employer's policy on
  using AI in applications.

## The three kinds of reel

| Reel | When | What is in it | Used for |
|---|---|---|---|
| Core Reel | Step 2, once per confirmed target job type | The 8 to 10 strongest approved cards for that job type, highest band and score first | Master resume, profile text, a 90-second introduction |
| Job Reel | Step 3, when the user decides to apply | 5 to 7 cards chosen from the Core Reel and re-ordered to match the posting | Tailored resume, opening lines for contacts, interview guide |
| Public Reel | Any time, optional | Cards with the Narrative field filled in, grouped by theme | Book chapters, posts |

The counts are targets, not minimums. With a small bank, use the cards that
qualify and say the reel is short. When there is no Core Reel, build the Job
Reel straight from the bank and say so. Each confirmed target job type has its
own Core Reel; build one at a time.

## Parts of this step

Follow the handoff rule in the shared rules between parts. Build one output
per reply, and show the short view first.

### Part 1. Cut the reel

Choose the cards. If a draft, or a card with no approved uses, is the only
card for a requirement, ask about it before leaving it out.

Show the reel and ask for approval, alone, before anything else:

```markdown
# Job Reel: <company>, <role>
Built from: Core Reel <job type>. Date: <date>.

| Order | Card | Score and band | Approved uses | Why this card for this audience |
|---|---|---|---|---|
| 1 | 04 <story title> | 78, Interview-ready | resume, interview | Shows the must-have on <requirement> |
```

Save reels in `story-bank/reels/`. Name Core Reels for the job type and Job
Reels for the company and role. Build nothing until the user approves. If the
user asks to build from an unapproved reel, label the output a draft.

After approval, any decisions that do not depend on each other (a card below
its band, a card with no approved uses) may be asked together in one panel.

When a card gains an approved use during this step, offer once to add it to
the reel.

### Part 2. Build the outputs, one at a time

Ask which output the user wants first. After each one, say what was built and
ask whether to go on to the next.

**From a Job Reel**

- **Resume changes.** A list of what to move up, cut or reword. Work against
  the master resume if there is one, otherwise the resume the user supplied.
  Put every line of the current resume under one of three labels:
  - *Built from a card:* the change, with the card id. Correct any line a card
    shows to be inaccurate and mark it as an accuracy correction.
  - *A card exists and cannot be used here:* say why (draft, not approved for
    resume use, below the band).
  - *No card:* nothing in the bank supports this line.

  Where a card supports a requirement, use the posting's own term for it. Use
  a posting term only where a card supports it.
- **Interview guide.** Likely questions; each reel story in a two-minute and
  a thirty-second version; and for each story the two tough answers from its
  card, which are the you-versus-team split and the skeptic answer. If a card
  has no skeptic answer, say so; do not write one.
- **Opening lines** for people the user knows at the company, with a reason
  for each contact. Skip this if the user names no one.

**From a Core Reel:** a master resume for the job type with each bullet tied
to a card id, profile text, and a 90-second introduction.

**From a Public Reel:** chapter or post drafts built from the Narrative,
Lessons and Quotes fields. Confirm that names and figures are cleared for
publication.

### Check these words

End every resume draft, interview guide, introduction and chapter draft with a
list headed "Check these words". Put on it every phrase in the output that
says or implies something not on a card: a reason, a sequence, a feeling, a
cause, who reported to whom, a stronger verb. Show each phrase with its card
id.

The user confirms or strikes each one.

- A confirmed phrase is written back to its card as the user's statement, and
  the card is re-scored.
- A struck phrase comes out of the output.

The output is a draft until the list is cleared. If there is nothing to list,
say "Check these words: none".

### Notes that stay with the user

A change log or summary may name a figure that was removed because it is not
cleared. Head any such section "For you only", so it is not copied into
something that is sent.

### Part 3. Close the step

List what was built, which cards it used, any claim left out for lack of
proof, and the open questions. Log the outputs in the position record. With
no folder, give the updated position record and reel as text to save, and the
bank index.

## After an interview

Run a 10-minute debrief: which questions were asked, which stories landed,
which did not, and what new facts the user recalled. Write anything new back to
the story cards, not to the reel, and re-score each card that changed. If an
interviewer pressed on a weak spot, add it to that card's `strengthen_next`.
Log the outcome in the position record.

## Fixed-choice questions in this step

| Question | Choices |
|---|---|
| Approval of a reel | Approve · Not yet |
| A card below the band its use needs | Use and flag · Strengthen first · Leave out |
| A draft that is the only card for a requirement | Use and flag · Leave out |
| A card with no approved uses (pick any) | Resume · Interview · Post · Book |
| Figures with clearance unknown in an output | All fine to share · Some are not · Not sure |
| Which output first | Resume changes · Interview guide · Opening lines |
| End of a part | Continue · Stop here |
