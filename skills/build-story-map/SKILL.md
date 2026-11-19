---
name: build-story-map
description: >
  This skill should be used when the user asks to "build my story map", "map my
  stories to skills", "what jobs do my stories support", "which roles should I
  target", or "build my Core Reel". It is Step 2 of the Career Track Record
  workflow: link every story card to skills, job types and proof, then use the
  map to choose target job types.
metadata:
  version: "0.1.0"
---

# Build the Story Map (Step 2)

The Story Map is the web of links between story cards and the skills they
prove, the job types they fit, the proof behind them and the people who can
back them up. The technical term is an ontology. It answers one question
quickly: "which of my stories prove I can do this job?"

Run this step after Step 1 (`build-story-bank`). If the bank has fewer than
five approved cards, say so and suggest building more first.

## Ground rules

- Never invent experience. The map shows only what the cards contain.
- Show weak spots plainly. A skill with one unvalidated story behind it is thin
  evidence, and the map must say so.

## Procedure

### 1. Read every card

Read all approved cards in `story-bank/cards/`. Collect each card's skill tags,
job-type tags, evidence and status.

### 2. Tidy the tags

Merge tags that mean the same thing ("pricing" and "pricing strategy"). Show
the user the merged list and confirm it before rewriting any card.

### 3. Write the map

Write `story-bank/story-map.md` with four sections:

1. **Skills.** A table with one row per skill: the cards that prove it, how
   many are validated, and a strength rating.
   - Strong: two or more validated cards.
   - Partial: one validated card, or unvalidated cards only.
   - Thin: a single unvalidated card.
2. **Job types.** For each job type, the cards that support it and the skills
   those cards cover.
3. **People and proof.** Each named person or document, and the cards it backs.
4. **Open questions.** Cards missing proof, and skills the user mentioned that
   no card supports.

### 4. Choose target job types

From the map, name the two or three job types with the strongest evidence. For
each, state the three skills that carry it and the one that is weakest. Ask the
user to confirm or change the targets.

When the user supplies real postings for a target, check the map against what
those postings ask for, and report any skill that appears in most postings but
is missing or thin on the map.

### 5. Build a Core Reel for each target

A Core Reel is the eight to ten strongest approved cards for one job type,
strongest first. Use the `cut-highlight-reel` skill to build it. If the bank
has fewer than eight suitable cards, build a shorter reel and say so.

## Keeping the map current

Rebuild the affected rows whenever a card is added, changed or validated. The
map is derived from the cards. When the two disagree, the cards win.

## When finished

Report the target job types, the strongest and weakest skills for each, and the
open questions. Suggest Step 3, the `check-a-position` skill, when the user has
a posting to consider.
