---
name: cut-highlight-reel
description: "This skill should be used when the user asks to \"cut a highlight reel\", \"build my Core Reel\", \"build a Job Reel\", \"tailor my resume to this job\", \"prepare me for this interview\", \"write an interview guide\", \"debrief my interview\", or \"pick stories for my book or posts\". It is Step 4 of the Career Track Record workflow: select the right story cards for one purpose and build the materials from them.\n"
metadata:
  version: "0.1.4"
---

# Cut a highlight reel (Step 4)

Part of Career Track Record v0.1.4. If the user asks which version is in use,
say v0.1.4.

A highlight reel is a hand-picked set of story cards for one audience. Think of
the Story Bank as all the game film from a career and a reel as the best plays
chosen for one viewer. Every resume, interview guide or chapter is built from a
reel, not from the whole bank.

## Ground rules

- **Never invent experience.** Every line in every output must trace to a story
  card. If the bank cannot support a claim, say so and leave the claim out.
- **Flag weak cards.** If a reel uses an unvalidated or unapproved card, say so
  and ask whether to fix it first. Each use has a band it should meet: resume
  lines need Resume-ready, an interview guide needs Interview-ready, book
  chapters and public posts need Proven. A card below that band may still be
  used if the user agrees; flag it with its score and its `strengthen_next`
  items, and offer a strengthen session.
- **Respect approved uses.** Use a card only for a use in its approved uses.
  Resume covers the resume and profile text. Interview covers the interview
  guide and the 90-second introduction. Post and book cover those. If the list
  is empty, ask the user before building.
- **Handle figures by clearance.** A figure marked not cleared never appears
  in an output: remove it, say so, and do not supply a substitute. A figure
  with clearance unknown may appear in a draft only: list every such figure
  under "Confirm before sending", and label the output a draft until the user
  has confirmed each one. Cleared figures are used freely.
- **Say whose account it is.** When a card is marked "role: own account", keep
  that note beside any line built from it.
- **A reel points to cards. It never copies them.** A reel holds card ids and
  reasons. Fix a story once in the bank and every reel is current.
- **The user writes their own answers.** For free-text application questions
  and cover notes, ask for the user's own first draft and refine it. Do not
  write these from scratch. Remind the user to check the employer's policy on
  using AI in applications.
- **When the user does not know, or does not decide, do not guess.** Record it
  as an open question, say what it blocks, and move on.
- **No working folder?** Keep the reel in the conversation and give the user
  the text to save.

## The three kinds of reel

| Reel | When | What is in it | Used for |
|---|---|---|---|
| Core Reel | Step 2, once per confirmed target job type | The 8 to 10 strongest approved cards for that job type, highest band and score first | Master resume, profile text, a 90-second introduction |
| Job Reel | Step 3, when the user decides to apply | 5 to 7 cards chosen from the Core Reel and re-ordered to match the posting | Tailored resume, opening lines for contacts, interview guide |
| Public Reel | Any time, optional | Cards with the Narrative field filled in, grouped by theme | Book chapters, posts |

**When the bank is small.** The counts are targets, not minimums. Use the cards
that qualify, even if that is three, and say the reel is short. Never add a
weak card to reach a number.

**When there is no Core Reel.** Build the Job Reel straight from the bank and
say so.

**One Core Reel per target.** Each confirmed target job type has its own Core
Reel. Build one at a time.

**Keep reels current.** A Job Reel may use any approved card that fits the
posting, including one built during the gap check. Add that card to the
matching Core Reel as well, and say so.

## Reel format

Save reels in `story-bank/reels/`. Name Core Reels for the job type and Job
Reels for the company and role.

```markdown
# Job Reel: <company>, <role>
Built from: Core Reel <job type>. Date: <date>.

| Order | Card | Score and band | Why this card for this audience |
|---|---|---|---|
| 1 | 04 <story title> | 78, Interview-ready | Proves the must-have on <requirement> |
```

Show the reel to the user and get approval before building anything from it.
If the user does not approve, stop and ask what to change. Build from an
unapproved reel only if the user asks, and label the output as a draft.

## What to build from a reel

**From a Core Reel**

- A master resume for the job type, each bullet tied to a card id.
- Profile text for the user's professional networking page.
- A 90-second introduction the user can say aloud.

**From a Job Reel**

- A list of resume changes: what to move up, cut or reword, each tied to a
  card. Work against the master resume if there is one, otherwise against the
  resume the user supplied. Cover the posting's key terms only where a card
  supports them. Correct any resume line that a card shows to be inaccurate,
  even if that card is not in the reel, and mark it as an accuracy correction.
  List resume lines that no card supports under "Not checked".
- An interview guide: likely questions, each reel story in a two-minute and a
  thirty-second version, and answers to the two tough questions from the story
  session.
- Opening lines for people the user knows at the company, with a reason for
  each contact.

**From a Public Reel**

- Chapter or post drafts built from the Narrative, Lessons and Quotes fields.
  Confirm that names and figures are cleared for publication.

## After an interview

Run a 10-minute debrief: which questions were asked, which stories landed,
which did not, and what new facts the user recalled. Write anything new back to
the story cards, not to the reel, and re-score each card that changed. If an
interviewer pressed on a weak spot, add it to that card's `strengthen_next`.
Log the outcome in the position record.

## When finished

List what was built, which cards it used, any claim left out for lack of proof,
and the open questions.
