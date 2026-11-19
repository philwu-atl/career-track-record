---
name: cut-highlight-reel
description: >
  This skill should be used when the user asks to "cut a highlight reel",
  "build my Core Reel", "build a Job Reel", "tailor my resume to this job",
  "prepare me for this interview", "write an interview guide", "debrief my
  interview", or "pick stories for my book or posts". It is Step 4 of the
  Career Track Record workflow: select the right story cards for one purpose and
  build the materials from them.
metadata:
  version: "0.1.0"
---

# Cut a highlight reel (Step 4)

A highlight reel is a hand-picked set of story cards for one audience. Think of
the Story Bank as all the game film from a career and a reel as the best plays
chosen for one viewer. Every resume, interview guide or chapter is built from a
reel, not from the whole bank.

## Ground rules

- **Never invent experience.** Every line in every output must trace to a story
  card. If the bank cannot support a claim, say so and leave the claim out.
- **Flag unvalidated cards.** If a reel uses one, say so and ask whether to
  validate it first.
- **A reel points to cards. It never copies them.** A reel file holds card ids
  and reasons. Fix a story once in the bank and every reel is current.
- **The user writes their own answers.** For free-text application questions
  and cover notes, ask for the user's own first draft and refine it. Do not
  write these from scratch. Remind the user to check the employer's policy on
  using AI in applications.

## The three kinds of reel

| Reel | When | What is in it | Used for |
|---|---|---|---|
| Core Reel | Step 2, once per target job type | The 8 to 10 strongest approved cards for that job type, strongest first | Master resume, profile text, a 90-second introduction |
| Job Reel | Step 3, when the user decides to apply | 5 to 7 cards chosen from the Core Reel and re-ordered to match the posting | Tailored resume, opening lines for contacts, interview guide |
| Public Reel | Any time, optional | Cards with the Narrative field filled in, grouped by theme | Book chapters, posts |

## Reel file format

Save reels in `story-bank/reels/`. Name Core Reels for the job type and Job
Reels for the company and role.

```markdown
# Job Reel: <company>, <role>
Built from: Core Reel <job type>. Date: <date>.

| Order | Card | Why this card for this audience |
|---|---|---|
| 1 | 04 <story title> | Proves the must-have on <requirement> |
```

Show the reel to the user and get approval before building anything from it.

## What to build from a reel

**From a Core Reel**

- A master resume for the job type, each bullet tied to a card id.
- Profile text for the user's professional networking page.
- A 90-second introduction the user can say aloud.

**From a Job Reel**

- A list of resume changes against the master resume: what to move up, cut or
  reword, each tied to a card. Check that the posting's key terms are covered
  only where a card supports them.
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
the story cards, not to the reel. Log the outcome in the position file.

## When finished

List what was built, which cards it used, and any claim left out for lack of
proof.
