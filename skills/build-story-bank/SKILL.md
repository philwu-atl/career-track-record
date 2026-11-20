---
name: build-story-bank
description: "This skill should be used when the user asks to \"build my story bank\", \"start my career track record\", \"build my track record\", \"capture my career accomplishments\", \"turn my resume into stories\", \"add a story\", \"run a story session\", or \"strengthen a card\". It is Step 1 of the Career Track Record workflow: load career documents, draft story cards, and fill the gaps in each card through a short guided session sized to what the card is for.\n"
metadata:
  version: "0.1.6"
---

# Build the Story Bank (Step 1)

Part of Career Track Record v0.1.6. If the user asks which version is in use,
say v0.1.6.

The Story Bank is the one place every career story is kept. Each accomplishment
is stored once, as a story card. Every later step reads from the bank, so
accuracy here matters more than polish.

## Read first

Read `references/shared-rules.md` before anything else. It holds the rules on
accuracy, proof, how much to check, confidential figures, bands, asking,
showing, handoffs and saving. They apply to this whole step.

Also read `references/story-card-template.md` (the card, its score and the
card view) and `references/story-session.md` (how a session runs).

## Three things to track on every card

- **Status** says how far the card has come: `starter` (one line), `draft`
  (built out, not yet approved by the user) or `approved` (the user has
  confirmed the content is right).
- **Proof** says whether there is evidence: `validated` or `unvalidated`, with
  `result_proof` and `role_proof` recorded separately.
- **Score and band** say how ready the card is for use, from Starter to Proven,
  with `strengthen_next` naming what would raise it.

They are separate. A card can be approved but unvalidated (the user stands by
it, with no proof on file), or validated but still a draft.

## Depth

Each card has a depth that sets how many questions its session asks and when
it stops: Quick, Standard or Deep. The caps and targets are in
`references/story-session.md`. Depth changes how much is asked, never how
accurate the card is. A Quick card is shorter, not looser.

Do not make the user pick from a menu. Recommend a depth from what the card is
for, and let the user change it:

- **Exploring or networking:** Quick for all cards.
- **Applying:** Standard for the shortlisted cards that fit the target, Quick
  for the rest.
- **Interview booked, an executive role, or a book chapter:** Deep for the
  three to five cards most likely to be used, Standard for the rest.

If the user gives no job stage, use Standard and say so. Record the stage and
default depth in `settings.md`.

## Parts of this step

The step has five parts. Follow the handoff rule in the shared rules between
them: say what was done, say what comes next, let the user choose, and do not
start the next part in the same reply.

### Part 1. Load the documents

Tell the user, in two lines, how much will be checked (see "How much to
check" in the shared rules). Record `validation: take my word` in
`settings.md` unless the user names another level.

Ask once for resumes, bios, a LinkedIn profile export, performance reviews,
memos, voice-memo transcripts and any other record of the user's work. Read
everything supplied before drafting.

If the user says to work from one document only, accept that, note in one line
that other records can be added later, and do not ask again. If the user names
a document but does not supply it, ask for it once, then go on with what is
there and list it as an open item.

### Part 2. Story starters

List one story starter for each distinct accomplishment the documents support:
one line each, result first, with the role and the year, or the role's date
range when the year is not known. Number them; the number becomes the card id.
A long career may yield 20 to 40. A short resume may yield five or six. Do not
pad the list. Merge duplicates that appear in more than one document. A line
with no result, such as "responsible for vendor relationships", is not an
accomplishment: list it separately as "no result stated" and do not number it.

Present the list and ask one question about it as a whole, in plain words:
reply "keep all", or say which numbers to drop or merge and what is missing.
Do not ask about each starter in turn.

### Part 3. Shortlist

Ask what kind of position the user is aiming for. If the user does not name a
target, leave it open, rank by evidence alone, and say so. Do not infer the
target. If the user asks what the documents suggest, offer a direction, say it
is a reading of the documents, and record nothing unless they choose it.

Then ask where they are: exploring, applying or interviewing.

Rank the starters by how much evidence they carry and how relevant they are.
Propose up to 10 or 12 to build out first, each with a recommended depth. The
rest stay as starters.

End the part by asking **which story to work on first**. Suggest the top of
the shortlist. The user chooses.

### Part 4. Story sessions

For the story the user chose, fill in the card template from the documents.
Leave unknown fields empty and mark them. Compute a first score. Link
overlapping stories in `related_cards`.

Then run the session in `references/story-session.md`. After each card
closes, say what was done and ask which story comes next, or whether to stop.
Three or four stories is a full sitting.

Validation follows the shared rules. When only the user's own account
supports their role, set `role_proof: own account`. That does not block
validation of the result. When a source proves only part of the result, mark
result proof partial and say which part is unproven.

### Part 5. Close the step

Show the bank overview: one line per card with its id, title, status, proof,
score, band and top `strengthen_next` item, highest score first. Draw it as a
visual with a score bar per card when the session can. Otherwise use a short
table. Then list the open questions.

Offer the Story Bank workbook once: a spreadsheet of the bank the user can
sort and filter. If they say yes, or ask for it at any time, follow
`references/bank-workbook.md`.

With no folder, give the bank index (see "Saving" in the shared rules).

Suggest Step 2, the `build-story-map` skill.

## Strengthening a card later

When the user asks to strengthen a card, or Step 3 sends them back to one, run
the strengthen session in `references/story-session.md`.

When the user states a new fact about a card outside a session, record it as
their statement, say what changed, and re-score. Do not ask questions about
it. If the statement conflicts with what the card already says, hold the
change and ask which is right.

## Fixed-choice questions in this step

| Question | Choices |
|---|---|
| Where the user is in their search | Exploring · Applying · Interviewing |
| Offer of the spreadsheet | Yes · Not now |
| End of a part | Continue · Stop here |

The story session has its own list in `references/story-session.md`.
