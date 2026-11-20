---
name: build-story-map
description: "This skill should be used when the user asks to \"build my story map\", \"map my stories to skills\", \"what jobs do my stories support\", \"which roles should I target\", or \"build my Core Reel\". It is Step 2 of the Career Track Record workflow: link every story card to skills, job types and proof, then use the map to choose target job types.\n"
metadata:
  version: "0.1.6"
---

# Build the Story Map (Step 2)

Part of Career Track Record v0.1.6. If the user asks which version is in use,
say v0.1.6.

The Story Map is the web of links between story cards and the skills they
show, the job types they fit, the proof behind them and the people who can
back them up. The technical term is an ontology. It answers one question
quickly: "which of my stories show I can do this job, and how well proven is
each?"

Run this step after Step 1 (`build-story-bank`).

## Read first

Read `references/shared-rules.md` before anything else. It holds the rules on
accuracy, proof, how much to check, confidential figures, bands, which cards a
step may use, asking, showing, handoffs and saving.

Two rules matter most here:

- **The map shows only what the cards contain.**
- **Show weak spots plainly.** A skill that rests on one unproven story, or on
  stories where the user's own part is unproven, is thin evidence, and the map
  must say so.

## A small bank

The map works best with five or more approved cards. With fewer, say so, build
the map from what exists and label it **provisional**. If a draft is the only
card for a skill or a job type, ask whether to include it, and flag it if the
user says yes. Otherwise leave drafts off and say so.

## Parts of this step

The step has four parts. Follow the handoff rule in the shared rules between
them, and do not start the next part in the same reply.

### Part 1. Read the cards and tidy the tags

Read the approved cards in `story-bank/cards/` and `settings.md`. Collect each
card's skill tags, job-type tags, evidence, status, result proof, role proof,
score and band. Starters are not cards and do not go on the map; list them
under open questions.

Check the tags and propose changes of three kinds:

- **Merge** tags that mean the same thing ("pricing" and "pricing strategy").
- **Remove** a skill tag from a card whose Actions or Result do not show that
  skill. A card counts toward a skill only when what the user did, or what
  resulted, shows it. A title, an award with no stated reason, or a skill the
  role merely involved does not show a skill.
- **Move** scope out of the skill tags. Team size, number of sites and budget
  are scope, not skills.

Show all proposed changes together and ask once for confirmation. Change no
card until the user confirms. If nothing needs changing, do not ask. If the
user has a doubt about one tag, treat it as its own question on a later turn.

### Part 2. Write the map

Write `story-bank/story-map.md` with five sections.

**1. Skills.** One row per skill, one column per card on the map. Mark each
card that shows the skill:

| Mark | Meaning |
|---|---|
| `V+` | Result proof covers the result that shows the skill, and the user's role is backed by a document or a named person |
| `V` | Result proof covers it, and the user's role rests on their own account |
| `U` | The card shows the skill and nothing on file covers the result |

Then give three counts and a support level:

- **Proven cards:** the number of `V+` and `V` marks.
- **Role backed:** the number of `V+` marks.
- **Support:** Well supported (two or more proven cards), Supported (one), or
  Thin (none).

When a skill's proven cards are all `V`, say beside the level "role: own
account". When they rest on one document or one person, say so. These levels
describe how much evidence the bank holds. They are different from the Strong,
Partial and Gap ratings used when checking one position, and from a card's
band.

**2. Scope.** One row, built from the Role and scope lines the user has
confirmed. List each part (team size, sites, budget) with its source. Label it
**proven** when every part has a source, **partly proven** when some do, and
**own account** when none do.

**3. Job types.** For each job type, the cards that support it and the skills
those cards cover.

**4. People and proof.** Each named person or document, the cards it backs,
and what it covers. Mark each person "not contacted" or "agreed to confirm".

**5. Open questions.** Cards missing proof or approval, cards in the Starter
band, unconfirmed scope, figures that are not cleared or have clearance
unknown, starters not yet built out, drafts left off, and skills the user said
they want to show that no card supports.

Show the Skills section as a grid. Draw it as a visual when the session can.
Otherwise use the table. Name the two or three weakest spots in plain words.
Anything that is a reading of the cards, such as "the weakest skill" or "what
this blocks", is labelled as a reading.

If the user keeps a Story Bank workbook, offer to refresh it with a **Story
Map** sheet: the same grid and counts, with the Scope row last. If
`settings.md` says the user keeps one and no file exists, offer to build it.

### Part 3. Choose target job types

Name up to three job types with the best support. Rank by the number of
proven cards behind each, then by role-backed cards, then by the bands of
those cards. Do not name a job type that rests on a single card unless the
user asks; say which single-card job type is strongest.

For each target, state the skills that carry it and the one that is weakest.
Where the weakest skill rests on a card below Interview-ready, name that card
and its top `strengthen_next` item.

Ask the user to confirm or change the targets. If the user does not confirm,
record the targets as provisional in `settings.md` and on the map, say what
would help them decide, and stop before the Core Reel. Do not push.

When the user supplies several real postings for a target, check the map
against what they ask for, and report any skill most of them require that is
missing or thin. With a single posting, use the `check-a-position` skill.

### Part 4. Hand off to the Core Reel

A Core Reel is the eight to ten strongest approved cards for one job type,
ranked by band and score, then by relevance. With a small bank it will be
shorter; say how many cards qualify. Each confirmed target gets its own Core
Reel, built one at a time with the `cut-highlight-reel` skill. Ask which
target to start with, and suggest the one with the best support. Building the
reel is part of that skill, not this one.

With no folder, give the map as text to save, and the bank index.

## Keeping the map current

Rebuild the affected rows whenever a card is added, changed, approved or
validated. The map is derived from the cards. When the two disagree, the cards
win.

When a card is approved after a Core Reel exists, add it to every Core Reel
whose job type it is tagged with, re-order that reel, and tell the user.

## Fixed-choice questions in this step

| Question | Choices |
|---|---|
| Proposed tag changes | Confirm · Not yet |
| A draft that is the only card for a skill or job type | Include and flag · Leave off |
| Target job types | Confirm these · Not sure yet |
| Which Core Reel first | one choice per confirmed target |
| End of a part | Continue · Stop here |

## When finished

Report the target job types and whether they are confirmed, the best and
weakest supported skills for each, and the open questions. Suggest Step 3, the
`check-a-position` skill, when the user has a posting to consider.
