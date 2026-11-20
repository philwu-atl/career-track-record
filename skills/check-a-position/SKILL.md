---
name: check-a-position
description: "This skill should be used when the user shares a job posting and asks \"is this a fit\", \"check this job\", \"should I apply\", \"run the fit check\", \"run the gap check\", or \"what am I missing for this role\". It is Step 3 of the Career Track Record workflow: score the fit against the Story Bank, find the gaps on the Story Map, close them by capturing stories or planning training, and support the decision.\n"
metadata:
  version: "0.1.6"
---

# Check a position (Step 3)

Part of Career Track Record v0.1.6. If the user asks which version is in use,
say v0.1.6.

Step 3 is a feedback loop between the Story Bank and the Story Map. It runs
each time the user considers a position, and answers three questions: how well
does this position fit, which skills does the user have but need to clarify,
and which skills are new? Every answer ends with a new or updated story card
stored in the bank.

Run this step after Steps 1 and 2. If there is no bank yet, say so and offer to
start with `build-story-bank`. If there is a bank but no map, read the cards
directly and say the map is missing.

## Read first

Read `references/shared-rules.md` before anything else. It holds the rules on
accuracy, proof, how much to check, confidential figures, bands, which cards a
step may use, asking, showing, handoffs and saving.

Three rules matter most here:

- **Give an honest fit check.** State weaknesses as plainly as strengths. Do
  not raise a rating to be encouraging.
- **A gap stays a gap.** A requirement with no card behind it is a gap, even
  if the user's background makes it seem likely.
- **A rating rises on what is on a card, never on a yes.**

## Parts of this step

The step has three parts: the fit check, the gap check and the decision.
Follow the handoff rule in the shared rules between them, and do not start the
next part in the same reply.

### Part 1. Load the position and run the fit check

Read the posting. List what it asks for, split into must-have and preferred
requirements. Save a record in `story-bank/positions/` named for the company
and role.

For each requirement, name the cards that show it, and rate it:

| Rating | When |
|---|---|
| **Strong** | An approved card shows it directly, its proof covers it, and the card is Interview-ready or Proven |
| **Partial (unproven)** | An approved card shows it directly, and the proof is missing, or the role rests on the user's own account |
| **Partial (thin card)** | An approved card shows it directly, with proof, and the card is below Interview-ready |
| **Partial (loose match)** | A card is related, and it takes interpretation to say it meets the requirement |
| **Gap** | No card. A starter or a draft the user has not agreed to use is not evidence; note that it exists. |

Directly means the card's own actions or result are what the requirement asks
for. Counting a driver training program as a safety program takes
interpretation, so it is a loose match.

A requirement about scope, such as team size, number of sites or budget, is
shown by the Role and scope line of a card. It is Strong only when the user
has confirmed that line and a document or person covers it. Confirmed by the
user alone is Partial (unproven).

Every Partial says why, and what would make it Strong, in one line. For
example: "Partial (unproven): team of 10 confirmed by you, no document or
person on file. One named person who agrees to confirm it would make this
Strong."

Report:

1. A scorecard. Count **matched** and **proven** separately, for must-haves
   and for preferred items. Matched means Strong, Partial (unproven) or
   Partial (thin card). Proven means Strong. For example: "Must-haves: 4 of 5
   matched, 2 proven, 1 gap." Draw the scorecard as a visual when the session
   can.
2. Each requirement on one line: its rating, the cards behind it with their
   scores, and the reason.
3. Three to five strengths, each with the card that backs it.
4. Three to five weaknesses.
5. A provisional recommendation, to be settled after the gap check.

The full table always goes in the position record. If the user has another
tool's match label for the same posting, record it beside this result and note
any disagreement.

### Part 2. Gap check

Go through each requirement rated Gap or Partial, one at a time. Skip one that
a card built earlier in this gap check has already resolved. What to do
depends on why the rating fell short.

**A loose match.** Ask, in plain words, what the user did that makes it
count: "The posting asks for a safety program. Your card describes rolling
out driver training. What did you do there that was safety work?" Do not
offer a yes button.

- If the user gives a sentence, write it to the card's Actions as their
  statement, say what changed, and rate the requirement again by the table
  above. The rating follows what the card now shows.
- If the user says only "yes", or says it counts without saying what they did,
  leave it Partial (loose match) and note "user says the link holds".
- If the user says no or is not sure, leave it as it is and record an open
  question.

**Unproven.** What happens depends on the validation level.

- At **take my word**, do not ask. After the fit check, say once which
  must-haves would turn Strong with proof and how many questions that would
  take, and offer: check the key stories for this job now, or later.
- At **check the key stories** or **check everything**, ask the Evidence
  question for that card alone. Do not run a full session.

**Thin card.** Say what this job needs from the card, then offer a strengthen
session on it: only the `strengthen_next` items that bear on the requirement.
The user can accept, or leave it and come back later. Re-score the card and
the requirement afterwards.

**No card.** Ask "Have you done this, and it is just not in the bank yet?"

- **Yes.** Run a story session for that story (see the `build-story-bank`
  skill), at Standard depth, or Deep if an interview is booked. Store the
  card, update the Story Map, add the card to any Core Reel whose job type it
  is tagged with, and rate the requirement again. If the answer is a fact
  about the user's background and not a story, such as the industry they
  worked in, record it on the Role and scope line of the cards it applies to,
  marked as the user's own account.
- **No.** List the gap as a training item: a course or a project. If web
  search is available, use it to name a real resource and say where it came
  from. If not, describe the kind of training and let the user choose one. Do
  not present a resource as vetted. If the source does not state how long it
  takes, write "duration not stated". When an item is completed, record it as
  a new story card with its proof, update the map, and re-score.
- **Not sure.** Leave the rating as it is and record an open question.

Do not suggest that another card could stand in for the missing one.

### Part 3. Decide

Show the updated scorecard with a final recommendation, and ask the user to
choose:

| Decision | What happens next |
|---|---|
| Apply | Use the `cut-highlight-reel` skill to build the Job Reel and the application materials. |
| Upgrade skills | Write the development plan, most important item first. Keep the position and re-score it as items are completed. |
| Hold | Keep the position with its fit check. Re-score when the bank or a reel changes. |
| Not pursue | Ask whether to keep watching it. If not, archive it with its fit check. |

When the user chooses Apply, the validation level is take my word, and the
offer to check the key stories was not already made for this position, say
once: employers may check references or ask for proof, and "check the key
stories" will add proof questions for the cards behind this job's must-haves.
Do not ask the questions unless the user says so.

Record the decision and the date in the position record. If the user does not
decide, record the position as undecided, list what would help them decide,
and stop. Do not build application materials for an undecided position unless
the user asks, and label anything built that way as a draft.

If the user keeps a Story Bank workbook, offer to refresh it and add the
position to the **Positions** sheet: one row per requirement, with company,
role, requirement, must-have or preferred, rating, cards with scores, reason,
decision and date.

With no folder, give the position record as text to save, and the bank index.

## Fixed-choice questions in this step

| Question | Choices |
|---|---|
| No card | Yes, I have done this · No, it is new · Not sure |
| Check the key stories for this job | Check now · Later |
| Offer of a strengthen session | Strengthen now · Later |
| The decision | Apply · Upgrade skills · Hold · Not pursue · Not decided |
| End of a part | Continue · Stop here |

The loose-match question is always asked in plain words.

## When finished

State the decision, what was added to the bank, any card left below
Interview-ready that backs a must-have (with its `strengthen_next` items), the
open questions, and the next action.
