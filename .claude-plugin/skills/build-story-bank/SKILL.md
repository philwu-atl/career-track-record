---
name: build-story-bank
description: >
  This skill should be used when the user asks to "build my story bank",
  "start my career track record", "build my track record", "capture my career
  accomplishments", "turn my resume into stories", "add a story", or "run a
  story session". It is Step 1 of the Career Track Record workflow: load career
  documents, draft story cards, and fill the gaps in each card through a short
  guided session.
metadata:
  version: "0.1.1"
---

# Build the Story Bank (Step 1)

The Story Bank is the one place every career story is kept. Each accomplishment
is stored once, as a story card with proof behind it. Every later step reads
from the bank, so accuracy here matters more than polish.

## Ground rules

Apply these in every step of the workflow.

1. **Never invent experience.** Record only what the user did, in facts the
   user supplies or confirms. Do not add numbers, titles, scope or outcomes the
   user has not stated. If a field is unknown, leave it empty and mark it.
2. **Separate "I" from "we".** Ask what the user personally did versus what the
   team did. Prefer "led", "helped build" or "contributed to" over "built" when
   that is the accurate word.
3. **Require proof before validation.** See the validation rule below.
4. **Protect confidential information.** Before recording employer or client
   figures, ask once per card whether they are public or cleared for use. If
   the user does not know, record "clearance unknown" and remind them to check
   before the figure is used outside the bank. Keep the bank in the user's own
   workspace. Do not send its contents anywhere.
5. **When the user does not know, or does not decide, do not guess.** Leave the
   field, rating or decision as it is, record it as an open question, say what
   it blocks, and move on. Do not ask a follow-up to an "I don't know".

## Where the bank lives

When a working folder is available, keep the bank as plain files:

```
story-bank/
├── cards/         one file per story card (01-short-title.md)
├── story-map.md   built in Step 2
├── positions/     one file per position checked in Step 3
└── reels/         highlight reels built in Step 2 and Step 4
```

When no folder is available, keep everything in the conversation and give the
user each finished item as text to save. This applies to every step.

## Two things to track on every card

- **Status** says how far the card has come: `starter` (one line), `draft`
  (built out, not yet approved by the user) or `approved` (the user has
  confirmed the content is right).
- **Proof** says whether there is evidence: `validated` or `unvalidated`.

They are separate. A card can be approved but unvalidated (the user stands by
it, with no proof on file), or validated but still a draft (proof exists, the
user has not signed off). Later steps use approved cards. They may use a draft
only if the user agrees, and must flag it.

## Procedure

### 1. Load the documents

Ask for resumes, bios, a LinkedIn profile export, performance reviews, memos,
voice-memo transcripts and any other record of the user's work. Read everything
supplied before drafting. If the user names a document but does not supply it,
ask for it once, then go on with what is there and list it as an open item.

### 2. Draft story starters

List one story starter for each distinct accomplishment the documents support:
one line each, result first, with the role and year. A long career may yield 20
to 40. A short resume may yield five or six. Do not pad the list. Present it,
ask the user to accept, merge or reject each one, and ask what is missing.

### 3. Shortlist

Ask which kinds of position the user is aiming for, if known. Rank the starters
by how much evidence they carry and how relevant they are. Propose up to 10 or
12 to build out first. With fewer starters, build out the ones the user chooses.
The rest stay as starters.

### 4. Draft each story card

For each shortlisted story, fill in the card template in
`references/story-card-template.md` from the documents. Leave unknown fields
empty and mark them. Do not guess.

### 5. Run a story session

Follow `references/story-session.md`: show the draft, ask one question for each
empty or partial field, ask two tough questions, then ask the user to approve
the card. Run three or four stories per sitting, in shortlist order.

### 6. Validate and store

Mark a card's proof `validated` only when the result, and the user's part in
it, is backed by one of:

- a document the user holds or can point to;
- a public source found by search, shown to the user and confirmed by the user
  as correct and about them;
- a named person who can back it up.

Proof covers what it covers. A memo that proves a savings figure does not prove
the size of the team. Note in the Evidence field what the proof supports.

Store cards in `story-bank/cards/`. An unvalidated card can stay in the bank,
but later steps must flag it wherever it is used.

## When finished

Report how many cards are approved, how many are validated, how many are still
drafts or starters, and the open questions. Suggest Step 2, the
`build-story-map` skill.
