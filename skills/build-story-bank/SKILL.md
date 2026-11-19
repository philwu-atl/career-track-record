---
name: build-story-bank
description: >
  This skill should be used when the user asks to "build my story bank",
  "start my career track record", "build my track record", "capture my career accomplishments", "turn my resume
  into stories", "add a story", or "run a story session". It is Step 1 of the
  Career Track Record workflow: load career documents, draft story cards, and fill
  the gaps in each card through a short guided session.
metadata:
  version: "0.1.0"
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
3. **Require proof before approval.** See the validation rule below.
4. **Protect confidential information.** Before recording employer or client
   figures, ask whether they are public or cleared for use. Keep the bank in
   the user's own workspace. Do not send its contents anywhere.

## Where the bank lives

When a working folder is available, keep the bank as plain files:

```
story-bank/
├── cards/         one file per story card (01-short-title.md)
├── story-map.md   built in Step 2
├── positions/     one file per position checked in Step 3
└── reels/         highlight reels built in Step 2 and Step 4
```

When no folder is available, keep the cards in the conversation and give the
user each approved card as text to save.

## Procedure

### 1. Load the documents

Ask for resumes, bios, a LinkedIn profile export, performance reviews, memos,
voice-memo transcripts and any other record of the user's work. Read all of
them before drafting anything.

### 2. Draft story starters

List 20 to 40 story starters: one line each, result first, with the role and
year. Present the list. Ask the user to accept, merge or reject each one and to
add any that are missing.

### 3. Shortlist

Ask which kinds of position the user is aiming for, if known. Rank the starters
by how much evidence they carry and how relevant they are. Propose the top 10
to 12 to build out first. The rest stay as one-line starters.

### 4. Draft each story card

For each shortlisted story, fill in the card template in
`references/story-card-template.md` from the documents. Leave unknown fields
empty and mark them. Do not guess.

### 5. Run a story session

A story session is a guided pass of about 15 minutes per story. Follow
`references/story-session.md`: show the draft, ask one question per empty
field, ask two tough questions, then ask the user to approve the card. Run
three or four stories per sitting, strongest first.

### 6. Validate and store

A card is **validated** only when its proof is one of:

- a document the user holds or can point to;
- a public source found by search, shown to the user and confirmed by the user
  as correct and about them;
- a named person who can back it up.

Mark each card `validated`, `unvalidated` or `starter`. Store approved cards in
`story-bank/cards/`. An unvalidated card can stay in the bank, but later steps
must flag it wherever it is used.

## When finished

Report how many cards are validated, unvalidated and still starters. Suggest
Step 2, the `build-story-map` skill.
