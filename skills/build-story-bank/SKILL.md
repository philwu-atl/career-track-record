---
name: build-story-bank
description: "This skill should be used when the user asks to \"build my story bank\", \"start my career track record\", \"build my track record\", \"capture my career accomplishments\", \"turn my resume into stories\", \"add a story\", \"run a story session\", or \"strengthen a card\". It is Step 1 of the Career Track Record workflow: load career documents, draft story cards, and fill the gaps in each card through a short guided session sized to what the card is for.\n"
metadata:
  version: "0.1.4"
---

# Build the Story Bank (Step 1)

Part of Career Track Record v0.1.4. If the user asks which version is in use,
say v0.1.4.

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
4. **Protect confidential information.** Ask once per figure the user supplies
   whether it is public or cleared for use, and carry the answer to every card
   that uses the figure. Record one of `cleared`, `cleared (public source)`,
   `not cleared` or `clearance unknown`. A figure that is not cleared never
   appears in anything meant to leave the bank. A figure with clearance unknown
   may appear only in a draft, listed under "Confirm before sending". Keep the
   bank in the user's own workspace. Do not send its contents anywhere.
5. **When the user does not know, or does not decide, do not guess.** Leave the
   field, rating or decision as it is, record it as an open question, say what
   it blocks, and move on. Do not ask a follow-up to an "I don't know". Do not
   infer an answer from indirect clues such as a file name.
6. **Depth changes how much is asked, never how accurate the card is.** A
   Quick card is shorter, not looser. Rules 1 to 5 apply at every depth.

## Where the bank lives

When a working folder is available, keep the bank as plain files:

```
story-bank/
├── settings.md    target job types, job stage and default depth
├── cards/         one file per story card (08-short-title.md)
├── story-map.md   built in Step 2
├── positions/     one file per position checked in Step 3
└── reels/         highlight reels built in Step 2 and Step 4
```

When no folder is available, keep everything in the conversation and give the
user each finished item as text to save. Give each card in the full template
format, header included, so later steps can read it when it is pasted back.
This applies to every step.

## Three things to track on every card

- **Status** says how far the card has come: `starter` (one line), `draft`
  (built out, not yet approved by the user) or `approved` (the user has
  confirmed the content is right).
- **Proof** says whether there is evidence: `validated` or `unvalidated`, with
  `result_proof` and `role_proof` recorded separately.
- **Score and band** say how ready the card is for use, from Starter to Proven,
  with `strengthen_next` naming what would raise it. See
  `references/story-card-template.md`.

They are separate. A card can be approved but unvalidated (the user stands by
it, with no proof on file), or validated but still a draft (proof exists, the
user has not signed off). Later steps use approved cards. They may use a draft
only if the user agrees, and must flag it.

## Depth

Each card has a depth that sets how many questions its story session asks and
when it stops: Quick (cap 4, target 40), Standard (cap 7, target 70) or Deep
(cap 10, target 85). See `references/story-session.md`.

Do not make the user pick from a menu. Recommend a depth from what the card is
for, and let the user change it:

- **Exploring or networking:** Quick for all cards.
- **Applying:** Standard for the shortlisted cards that fit the target, Quick
  for the rest.
- **Interview booked, an executive role, or a book chapter:** Deep for the
  three to five cards most likely to be used, Standard for the rest.

If the user gives no job stage, use Standard and say so. Record the stage and
default depth in `settings.md`. The user can change a card's depth at any time.

## Procedure

### 1. Load the documents

Ask once for resumes, bios, a LinkedIn profile export, performance reviews,
memos, voice-memo transcripts and any other record of the user's work. Read
everything supplied before drafting.

If the user says to work from one document only, such as a resume, accept
that: work from it, note in one line that other records can be added later,
and do not ask again. If the user names a document but does not supply it, ask
for it once, then go on with what is there and list it as an open item.

### 2. Draft story starters

List one story starter for each distinct accomplishment the documents support:
one line each, result first, with the role and the year, or the role's date
range when the year is not known. Number them; the number becomes the card id.
A long career may yield 20 to 40. A short resume may yield five or six. Do not
pad the list. Merge duplicates that appear in more than one section of a
document. Present the list, ask the user to accept, merge or reject each one,
and ask what is missing.

### 3. Shortlist and set depth

Ask one question: what kind of position the user is aiming for, and where they
are (exploring, applying, or interviewing). If the user does not name a target,
leave it open, rank by evidence alone, and say so. Do not infer the target.

Rank the starters by how much evidence they carry and how relevant they are.
Propose up to 10 or 12 to build out first, each with a recommended depth. With
fewer starters, build out the ones the user chooses. The rest stay as starters.

### 4. Draft each story card

For each shortlisted story, fill in the card template in
`references/story-card-template.md` from the documents. Leave unknown fields
empty and mark them. Do not guess. Compute a first score so the session knows
where to start. Link overlapping stories in `related_cards`.

### 5. Run a story session

Follow `references/story-session.md`: show the draft, ask about the items worth
the most points first, stop at the depth's target or cap, then close with
approval and the score. Run three or four stories per sitting, in shortlist
order.

### 6. Validate and store

Mark a card's proof `validated` when its result is backed by at least one of:

- a document the user holds or can point to;
- a public source found by search, shown to the user and confirmed by the user
  as correct and about them;
- a named person who can back it up.

Proof covers what it covers. A memo that proves a savings figure does not prove
the size of the team or who led the work. Record result proof and role proof
separately, and in the Evidence field record what each source covers: the
result, the user's role, the scope. For a named person, ask what they can
confirm. When only the user's own account supports their role, set
`role_proof: own account`. That does not block validation, but it caps the card
below Proven, and later steps must say so wherever the card is used.

When a source proves only part of the result (for example the program, but not
the user's own outcome), mark result proof partial and say which part is
unproven.

Store cards in `story-bank/cards/`. An unvalidated card can stay in the bank,
but later steps must flag it wherever it is used.

## Strengthening a card later

When the user asks to strengthen a card, or Step 3 sends them back to one, run
the strengthen session in `references/story-session.md`: ask only the
`strengthen_next` items, then re-score.

## When finished

Report, in a short table, each card's status, proof, score and band, and its
top `strengthen_next` item. Then list the open questions. Suggest Step 2, the
`build-story-map` skill.
