---
name: check-a-position
description: >
  This skill should be used when the user shares a job posting and asks "is
  this a fit", "check this job", "should I apply", "run the fit check", "run
  the gap check", or "what am I missing for this role". It is Step 3 of the
  Career Track Record workflow: score the fit against the Story Bank, find the gaps
  on the Story Map, close them by capturing stories or planning training, and
  support the decision.
metadata:
  version: "0.1.0"
---

# Check a position (Step 3)

Step 3 is a feedback loop between the Story Bank and the Story Map. It runs
each time the user considers a position, and answers three questions: how well
does this position fit, which skills does the user have but need to clarify,
and which skills are new? Every answer ends with a new or updated story card
stored in the bank.

Run this step after Steps 1 and 2. If there is no bank or map yet, say so and
offer to start with `build-story-bank`.

## Ground rules

- **Give an honest fit check.** State weaknesses as plainly as strengths. Do
  not raise a score to be encouraging.
- **Never invent experience.** A requirement with no card behind it is a gap,
  even if the user's background makes it seem likely.
- **Flag unvalidated evidence.** When a strength rests on an unvalidated card,
  say so.

## Procedure

### 3.1 Load the position

Read the posting. List what it asks for, split into must-have and preferred
requirements. Save a file in `story-bank/positions/` named for the company and
role.

### 3.2 Fit check

For each requirement, look up the Story Map and name the cards that prove it.
Rate each requirement:

- **Strong:** one or more validated cards prove it directly.
- **Partial:** related evidence, or unvalidated cards only.
- **Gap:** no card.

Report:

1. A table: requirement, rating, cards behind it, one-line reason.
2. An overall read in one sentence, counting must-haves separately from
   preferred items ("6 of 7 must-haves strong, 1 gap").
3. Three to five strengths, each with the card that backs it.
4. Three to five weaknesses.
5. A recommended decision.

If the user has another tool's match label for the same posting, record it
beside this result and note any disagreement.

### 3.3 Gap check

For each requirement rated Gap or Partial, ask one question at a time: "Have
you done this, and it is just not in the bank yet?"

### 3.4a Clarify a skill the user has

If yes, run a story session for that story (see the `build-story-bank` skill).
Validate it: the card needs proof from a document, a public source found by
search and confirmed by the user, or a named person who can back it up. Store
the card, update the Story Map, and re-score the position.

### 3.4b Identify a new skill

If no, list the gap as a training item: a course or a project, with a named
resource and an estimate of the time. If the user chooses to upgrade skills,
write the items into a development plan, most important first. When an item is
completed, record it as a new story card with its proof (a certificate or a
project result), update the map, and re-score.

### 3.5 Decide

Present the updated fit check and ask the user to choose:

| Decision | What happens next |
|---|---|
| Apply | Use the `cut-highlight-reel` skill to build the Job Reel and the application materials. |
| Upgrade skills | Write the development plan. Keep the position and re-score it as items are completed. |
| Hold | Keep the position with its fit check. Re-score when the bank or a reel changes. |
| Not pursue | Ask whether to keep watching it. If not, archive it with its fit check. |

Record the decision and the date in the position file. Whatever was learned in
this step is already stored in the bank, whichever decision is made.

## When finished

State the decision, what was added to the bank, and the next action.
