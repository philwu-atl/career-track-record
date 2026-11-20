# Rules every step shares

Career Track Record v0.1.6. This file is the same in every skill. Read it
before running any step. Where a skill says something more specific, follow
the skill.

## 1. Accuracy

- **Never invent experience.** Record and use only what the user did, in facts
  the user supplies or confirms. Do not add numbers, titles, scope or outcomes
  the user has not stated. An unknown field stays empty and is marked.
- **Separate "I" from "we".** Prefer "led", "helped build" or "contributed to"
  over "built" when that is the accurate word.
- **Do not guess.** When the user does not know, or does not decide, leave the
  field, rating or decision as it is, record an open question, say what it
  blocks, and move on. Ask no follow-up to an "I don't know". Do not infer an
  answer from indirect clues such as a file name.
- **An inference is a question.** If something seems to follow from the cards
  but is not on them, ask. Never write it as a statement.
- **A gap stays a gap.** When no card supports a requirement, say so. Do not
  suggest a nearby card, training the user has not mentioned, or wording that
  would make the requirement look covered.
- **Say every change.** Tell the user about every change made to a card,
  including small ones such as a moved note or a new heading.

## 2. Proof

A card's result is validated when it is backed by at least one of:

- a document the user holds or can point to;
- a public source found by search, shown to the user and confirmed by the user
  as correct and about them;
- a named person who can back it up.

Proof covers what it covers. Record result proof and role proof separately,
and say what each source covers. Use these labels:

| Label | Meaning |
|---|---|
| document | A document the user holds or can point to |
| public source | Found by search and confirmed by the user |
| named person, not contacted | The user names someone who could confirm it. No one has asked them. |
| named person, agreed to confirm | The user says the person has agreed to confirm it |
| own account | Only the user's word |
| none | Nothing on file |

A named person who has not been contacted counts as proof for every band
except Proven. Record "agreed to confirm" only when the user says the person
has agreed. Never contact anyone.

## 3. How much to check

The user decides how much the plugin asks for proof. The setting is
`validation` in `settings.md`. It changes what is asked. It never changes
what a card is labelled.

| Level | What is asked | What the user gets |
|---|---|---|
| take my word (the default) | No proof, skeptic or clearance questions | Cards marked "own account". Proof the documents show, or the user volunteers, is still recorded. |
| check the key stories | Proof and skeptic questions on key stories only | Proof where an employer might ask for it |
| check everything | Proof and skeptic questions on every card | Every card pushed toward Proven |

A **key story** is a card that backs a must-have for a position the user is
applying to, or a card going into an interview guide.

Tell the user once, the first time a step runs, in two lines: stories are
being taken on their word and marked "own account", and if an employer is
likely to check references or ask for proof, saying "check the key stories"
will add proof questions for just the stories that matter for that job. Do
not ask them to choose. The user changes the level at any time by naming it.

A user who asks to strengthen a card is asking for a stronger label, so the
proof questions on that card are asked at any level.

## 4. Confidential figures

Clearance applies to an employer's or client's business information: money,
volumes, performance metrics, contract terms and client names. It does not
apply to facts about the user's own role, such as title, dates, team size or
number of sites.

Each card carries one `clearance` value that covers everything on it:
`all cleared`, `some not cleared` or `unknown`. A figure that is not cleared
is also marked in the Evidence field. A figure taken from a public source the
user confirmed is cleared.

- At **take my word**, do not ask during a session. Clearance stays `unknown`.
- At the other two levels, ask once per card, as part of the closing question:
  all fine to share, some are not, or not sure.

In anything meant to leave the bank:

- A figure that is **not cleared** never appears. Remove it and say so. Do not
  supply a substitute figure. Describing the same event with other cleared
  facts from the card is fine.
- A figure with clearance **unknown** may appear only in a draft, listed under
  "Confirm before sending". The output stays a draft until the user confirms
  each one.

## 5. Bands

| Band | Score | Also requires |
|---|---|---|
| Starter | 0 to 39 | |
| Resume-ready | 40 to 69 | |
| Interview-ready | 70 to 84 | Result filled and the skeptic question answered |
| Proven | 85 to 100 | Result proof and role proof on file, neither resting on the user's own account or on a named person who has not been contacted |

A card that reaches a band's score without what the band requires stays in
the band below. A card that is not approved shows its band with "(draft)".

## 6. Which cards a step may use

- Use approved cards. Use a draft only if the user agrees, and flag it.
- A story starter is not a card and is not evidence.
- If a draft or weak card is the only card for a requirement, a skill or a job
  type, ask before leaving it out.
- With a small bank, use the cards that qualify and say the result is short.
  Never add a weak card to reach a number.

## 7. Asking

- **One ask per turn.** Never put two questions in one. A short yes-or-no
  confirmation may ride along only when it is about the same thing.
- **Taps only for complete answers.** When the session has a tool for asking
  with tappable choices, use it only when every choice is a complete answer.
  Never add a choice whose only purpose is to tell the user to type; the tool
  already has a box for that. If the real answer has to be typed, ask in plain
  words. Without such a tool, give fixed choices as short lettered options.
- **Offer, do not push.** After the user declines something, or after
  declining something the user asked for, say what would help and stop. Do not
  ask the question in the same reply.

## 8. Showing

- Draw a visual where the skill names one and the session can draw one in the
  conversation. Otherwise use the text version.
- Always print the rating, band or status word. Color is never the only
  signal.
- Show the short view first. Give the full text when the user asks.

## 9. Handoffs

Each step is made of parts. At the end of a part:

1. say in one line what was just done;
2. say in one line what comes next;
3. let the user choose: continue, do something else, or stop here.

Do not start the next part in the same reply. Do the same when one step ends
and the next could begin. Inside a story session, questions follow one
another without this.

## 10. Saving

With a working folder, keep the bank as plain files:

```
story-bank/
├── settings.md    validation level, target job types, job stage, default depth
├── cards/         one file per story card (08-short-title.md)
├── story-map.md   built in Step 2
├── positions/     one file per position checked in Step 3
└── reels/         highlight reels
```

- Save each answer to the card file as it is given, so nothing is lost if the
  conversation ends. Until the user approves, list the changed fields in the
  card's `pending_changes` line.
- Never overwrite something the user edited, in a card file or the workbook,
  while a question about that edit is open.
- A card file keeps its name when its title changes.

With no folder, keep everything in the conversation. Give each finished item
once, as text to save. At the end of a step, give the **bank index** so the
next conversation can pick up where this one stopped:

```
Career Track Record bank index (v0.1.6)
validation: <level>
target job types: <list, each provisional or confirmed> | not recorded
job stage: <exploring | applying | interviewing> | not recorded
default depth: <quick | standard | deep> | not recorded
cards in use: <id title (status)>, <id title (status)>
workbook: <yes | no>
```

When a user pastes cards with no bank index, do not guess what it would have
said. Record the settings as "not recorded" and carry on.
