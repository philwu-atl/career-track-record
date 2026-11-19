---
name: check-a-position
description: "This skill should be used when the user shares a job posting and asks \"is this a fit\", \"check this job\", \"should I apply\", \"run the fit check\", \"run the gap check\", or \"what am I missing for this role\". It is Step 3 of the Career Track Record workflow: score the fit against the Story Bank, find the gaps on the Story Map, close them by capturing stories or planning training, and support the decision.\n"
metadata:
  version: "0.1.4"
---

# Check a position (Step 3)

Part of Career Track Record v0.1.4. If the user asks which version is in use,
say v0.1.4.

Step 3 is a feedback loop between the Story Bank and the Story Map. It runs
each time the user considers a position, and answers three questions: how well
does this position fit, which skills does the user have but need to clarify,
and which skills are new? Every answer ends with a new or updated story card
stored in the bank.

Run this step after Steps 1 and 2. If there is no bank yet, say so and offer to
start with `build-story-bank`. If there is a bank but no map, read the cards
directly and say the map is missing.

## Ground rules

- **Give an honest fit check.** State weaknesses as plainly as strengths. Do
  not raise a rating to be encouraging.
- **Never invent experience.** A requirement with no card behind it is a gap,
  even if the user's background makes it seem likely.
- **Flag weak evidence.** When a strength rests on an unvalidated or
  unapproved card, or a card below Interview-ready, say so.
- **When the user does not know, or does not decide, do not guess.** Record it
  as an open question, say what it blocks, and move on.
- **No working folder?** Keep the position record in the conversation and give
  the user the text to save.

## Procedure

### 3.1 Load the position

Read the posting. List what it asks for, split into must-have and preferred
requirements. Save a record in `story-bank/positions/` named for the company
and role.

### 3.2 Fit check

For each requirement, name the cards that prove it. Rate each requirement:

- **Strong:** at least one approved, validated card proves it directly, and
  that card is Interview-ready or Proven.
  Directly means the card's own actions or result are what the requirement asks
  for. If it takes interpretation, such as counting a driver training program
  as a safety program, rate it Partial. The gap check asks the user whether
  the link holds.
- **Partial:** related evidence, or evidence that is unvalidated, unapproved,
  unconfirmed, or on a card below Interview-ready (score under 70).
- **Gap:** no card. A starter is not evidence: rate the requirement Gap and
  note that a starter exists.

A requirement about scope, such as team size, number of sites or budget, is
proven by the Role and scope line of a card. Rate it Strong only when the user
has confirmed that line and proof covers it. Confirmed without proof is
Partial.

Report:

1. A table: requirement, must-have or preferred, rating, cards behind it with
   their scores, one-line reason.
2. An overall read in one sentence, counting must-haves separately from
   preferred items ("3 of 4 must-haves strong, 1 gap").
3. Three to five strengths, each with the card that backs it.
4. Three to five weaknesses.
5. A provisional recommendation, to be settled after the gap check.

When a rating rests on a card marked "role: own account", say so in the reason.

If the user has another tool's match label for the same posting, record it
beside this result and note any disagreement.

### 3.3 Gap check

Go through each requirement rated Gap or Partial, one question at a time. Skip
a requirement that a card built earlier in this gap check has already
resolved. Choose the question by why the rating fell short:

- **A loose match.** Ask whether the link holds, for example "Does leading the
  rollout of a driver training program count as running a safety program?" If
  the user says yes, re-score. If no or not sure, leave it Partial and record
  an open question.
- **Proof or confirmation missing.** Ask the Evidence question alone. Do not
  run a full session.
- **Card too thin.** The right card exists but is below Interview-ready. Say
  what this job needs from it (for example, a commercial role needs the user's
  own revenue figure), then offer a strengthen session on that card: only its
  `strengthen_next` items that bear on the requirement. The user can accept,
  or leave it Partial and come back later. Re-score the card and the
  requirement afterwards.
- **No card.** Ask "Have you done this, and it is just not in the bank yet?"
  There are three answers, set out below.

### 3.4a Yes: clarify a skill the user has

Run a story session for that story at Standard depth, or Deep if an
interview is booked (see the `build-story-bank` skill). Ask for
approval and apply the validation rule: proof is a document, a public source
found by search and confirmed by the user, or a named person who can back it
up. Store the card, update the Story Map, add the card to any Core Reel whose
job type it is tagged with, and re-score the requirement.

If the answer is a fact about the user's background and not a story, such as
the industry they worked in, record it on the Role and scope line of the cards
it applies to, marked as the user's own account, and ask once what could back
it up.

### 3.4b No: identify a new skill

List the gap as a training item: a course or a project. If web search is
available, use it to name a real resource and say
where it came from. If not, describe the kind of training and let the user
choose one. Do not present a resource as vetted. If the source does not state
how long it takes, or there is no source, write "duration not stated". Do not
estimate it.

If the user chooses to upgrade skills, write the items into a development plan,
most important first. When an item is completed, record it as a new story card
with its proof (a certificate or a project result), update the map, and
re-score.

### 3.4c Not sure

Leave the rating as it is. Record the requirement as an open question and say
what would settle it. Do not run a session and do not add a training item.

### 3.5 Decide

Present the updated fit check with a final recommendation, and ask the user to
choose:

| Decision | What happens next |
|---|---|
| Apply | Use the `cut-highlight-reel` skill to build the Job Reel and the application materials. |
| Upgrade skills | Write the development plan. Keep the position and re-score it as items are completed. |
| Hold | Keep the position with its fit check. Re-score when the bank or a reel changes. |
| Not pursue | Ask whether to keep watching it. If not, archive it with its fit check. |

Record the decision and the date in the position record. If the user does not
decide, record the position as undecided, list what would help them decide, and
stop. Do not build application materials for an undecided position unless the
user asks, and label anything built that way as a draft.

Whatever was learned in this step is already stored in the bank, whichever
decision is made.

## When finished

State the decision, what was added to the bank, any card left below
Interview-ready that backs a must-have (with its `strengthen_next` items), the
open questions, and the next action.
