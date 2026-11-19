---
name: build-story-map
description: >
  This skill should be used when the user asks to "build my story map", "map my
  stories to skills", "what jobs do my stories support", "which roles should I
  target", or "build my Core Reel". It is Step 2 of the Career Track Record
  workflow: link every story card to skills, job types and proof, then use the
  map to choose target job types.
metadata:
  version: "0.1.1"
---

# Build the Story Map (Step 2)

The Story Map is the web of links between story cards and the skills they
prove, the job types they fit, the proof behind them and the people who can
back them up. The technical term is an ontology. It answers one question
quickly: "which of my stories prove I can do this job?"

Run this step after Step 1 (`build-story-bank`).

## Ground rules

- **Never invent experience.** The map shows only what the cards contain.
- **Show weak spots plainly.** A skill with one unvalidated story behind it is
  thin evidence, and the map must say so.
- **When the user does not know, or does not decide, do not guess.** Record it
  as an open question, say what it blocks, and move on.
- **No working folder?** Keep the map in the conversation and give the user the
  text to save.

## A small bank

The map works best with five or more approved cards. With fewer, say so, then
build the map from what exists and label it **provisional**. If the only cards
are drafts, ask whether to use them, and flag each one.

## Procedure

### 1. Read every card

Read the approved cards in `story-bank/cards/`, plus any drafts the user agreed
to include. Collect each card's skill tags, job-type tags, evidence, status and
proof. Starters are not cards and do not go on the map, but list them under
open questions.

### 2. Tidy the tags

Merge tags that mean the same thing ("pricing" and "pricing strategy"). Show
the user the merged list and confirm it before rewriting any card.

Check each tag against its card. A card counts toward a skill only when its
Actions or Result show that skill. A skill that rests on scope, such as leading
a large team, counts only when the user has confirmed the card's Role and scope
line.

### 3. Write the map

Write `story-bank/story-map.md` with four sections:

1. **Skills.** A table with one row per skill: the cards that show it, how many
   of those are validated, what the proof covers, and a support level.
   - **Well supported:** two or more validated cards.
   - **Supported:** one validated card.
   - **Thin:** unvalidated cards only.

   These levels describe how much evidence the bank holds. They are different
   from the Strong, Partial and Gap ratings used when checking one position.
2. **Job types.** For each job type, the cards that support it and the skills
   those cards cover.
3. **People and proof.** Each named person or document, the cards it backs, and
   what it proves.
4. **Open questions.** Cards missing proof or approval, unconfirmed scope,
   figures with clearance unknown, starters not yet built out, and skills the
   user mentioned that no card supports.

### 4. Choose target job types

From the map, name up to three job types with the best support. For each, state
the skills that carry it and the one that is weakest. Ask the user to confirm
or change the targets. If the user does not confirm, keep the targets marked
provisional and stop before the Core Reel.

When the user supplies several real postings for a target, check the map
against what they ask for, and report any skill most of them require that is
missing or thin on the map. With a single posting, use the `check-a-position`
skill instead.

### 5. Hand off to the Core Reel

A Core Reel is the eight to ten strongest approved cards for one job type.
Once the user has confirmed a target, offer to build its Core Reel with the
`cut-highlight-reel` skill. Building the reel is part of that skill, not this
one.

## Keeping the map current

Rebuild the affected rows whenever a card is added, changed, approved or
validated. The map is derived from the cards. When the two disagree, the cards
win.

## When finished

Report the target job types and whether they are confirmed, the best and
weakest supported skills for each, and the open questions. Suggest Step 3, the
`check-a-position` skill, when the user has a posting to consider.
