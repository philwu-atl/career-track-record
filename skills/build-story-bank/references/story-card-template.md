# Story card template

One file per story. Keep the header fields exactly as named so later steps can
read them. When there is no working folder, give the user the whole card in
this format, header included, so later steps can read it when it is pasted
back.

```markdown
---
id: 08
title: <one line, result first>
status: starter | draft | approved
proof: validated | unvalidated
result_proof: <label, source and what it covers> | none
role_proof: <label and source> | own account | none
clearance: all cleared | some not cleared | unknown
pending_changes: none
depth: quick | standard | deep
score: <0 to 100>
band: starter | resume-ready | interview-ready | proven
strengthen_next: [<item (+points)>, <item (+points)>, <item (+points)>]
complete: <fields filled> of 12
skill_tags: [<skill>, <skill>]
job_type_tags: [<job type>, <job type>]
approved_uses: []
related_cards: []
---

## Role and scope
Title, organization, team size, budget or P&L, dates.

## Situation
The business problem, in two sentences.

## Actions
What the user personally did, up to five things. Mark anything the team did.
One or two accurate actions are better than three padded ones. Record the
answer to "you versus the team" here.

## Obstacles
What made it hard. One specific conversation or decision.

## Result
The measured outcome, with the baseline and the time period.

## Evidence
Where the proof comes from: a document, a public source found by search, or a
named person who can back it up. Use the proof labels in the shared rules. Say
what each source covers (the result, the user's role, the scope). For a named
person, say what they can confirm and whether they are "not contacted" or have
"agreed to confirm". If the user's role rests on their own account, write
"role: own account". Mark any figure that is not cleared. Record the answer to
the skeptic question here.

## Lessons
What the user would repeat or change.

## Quotes
Lines the user said, or would say, word for word in an interview. A line that
Claude drafted at the user's request is recorded only if the user picks it and
confirms it is something they would say, and is marked
"(drafted with Claude, approved by user)".

## Narrative (optional)
A longer telling, for a book chapter or a post.
```

## Card view

The template above is how a card is stored. The card view is how a card is
shown to the user. It has two parts.

**Card header**

- Card id and title.
- Role, organization and dates on one line.
- Status and proof as short labels: `Draft` or `Approved`; `Result proof:
  <label>` or `No result proof`; `Role proof: <label>` or `Role: own account`.
  The labels are the ones in the shared rules, for example `document` or
  `named person, not contacted`.
- Score out of 100, band, and the depth's target score.
- Up to three strengthen-next items with their points.

**Card content**

Situation, Actions, Obstacles, Result, Evidence and Lessons, each in one or
two lines, in the user's own facts. Mark an empty field `(empty)` and a
partial one `(partial: <what is missing>)`. Leave out the header block, the
tag lists and the Narrative.

When the session can draw a visual, draw the card view as one card: the header
at the top, a bar showing the score with a mark at the target, the
strengthen-next items as a row, and the content fields below. Otherwise use
this text form:

```
Card <id> · <title>
<role>, <organization>, <dates>
<status> · <result proof label> · <role proof label>
Score <n> of 100 · <band> · target <n> (<depth>)
Strengthen next: <item (+points)> · <item (+points)> · <item (+points)>

Situation: <one or two lines>
Actions: <one or two lines>
Obstacles: <one or two lines>
Result: <one or two lines>
Evidence: <one or two lines>
Lessons: <one or two lines>
```

The card view never adds, rounds or rewords a fact. It shows what the stored
card holds, in less space. A figure marked not cleared may appear in the card
view, because the card view is shown only to the user.

## Card ids and related cards

- **Ids.** A card keeps the number its story starter had. Starter 8 becomes
  card `08`, saved as `08-short-title.md`. Numbers are never reused.
- **Related cards.** When two stories share people, a program or a result,
  list each in the other's `related_cards` with a few words on the link (for
  example `09 (same partner, later order)`). Do not merge them unless the user
  asks. Count a shared result on one card only; the other card points to it.

## Titles and file names

A title is one line with the result first. When the you-versus-team answer
changes the user's part, change the verb and keep the result first: "Cut
claims 38% by designing the checks the team ran", not "Led the work that cut
claims 38%". A card file keeps its name when its title changes.

## The header lines `clearance` and `pending_changes`

- `clearance` covers every employer or client figure on the card. It starts
  as `unknown`. See "Confidential figures" in the shared rules.
- `pending_changes` lists the fields changed since the user last approved the
  card, for example `[Result, Evidence]`. Set it back to `none` at approval.

## The twelve fields

Nine content fields: title, role and scope, situation, actions, obstacles,
result, evidence, lessons, quotes. Three tag fields: skill tags, job-type tags,
approved uses. Narrative is an optional thirteenth field.

## Tagging

- **Skill tags:** use a short, fixed list and reuse the same wording across
  cards (for example: pricing strategy, P&L turnaround, partner programs,
  change management, cross-border). Add a new tag only when no existing tag
  fits. Tag a card with a skill only when its Actions or Result show that
  skill. Do not tag a card with a skill just because the role involved it.
- **Job-type tags:** the kinds of position the story supports (for example:
  head of product, general manager, partnerships lead).
- **Approved uses:** where the user is willing to use the story. Any of:
  resume, interview, post, book. Leave the list empty until the user chooses.
  Nothing is approved by default.

Scope, such as team size, number of sites or budget, is not a skill tag. It
lives in Role and scope, and the Story Map reads it from there.

Proposed tags are shown in the read-back. When the user approves the read-back
without changing them, the tags are confirmed.

## Completeness

Count the filled fields out of twelve, using these rules:

- A field is **filled** when it holds the user's answer and nothing essential
  is missing.
- A field is **partial** when part is missing, such as a Result with no
  baseline or period, or a Situation with no "why then". Name what is missing.
  Count partial as not filled.
- An Evidence field that says there is no proof is **empty**.
- Tag fields count once the user has confirmed them. If the user confirms some
  proposed tags and not others, keep the confirmed ones, drop the rest, and
  count the field as filled.

A card with an empty Result or Evidence field is not ready to validate,
whatever its count. It can still be approved, because approval means the
content is accurate, not that it is proven.

## Card strength score

The score says how ready a card is for use. It does not measure whether the
card is true: every card, at every depth and every score, follows the ground
rules on accuracy. A low score means the card is short or thinly proven, never
that it is loose.

### Points (100 in total)

| Item | Points | Full points when |
|---|---|---|
| Result | 20 | A measured outcome with a baseline and a period |
| Actions | 15 | What the user personally did, with the "you versus the team" split |
| Result proof | 15 | A document, a confirmed public source or a named person covers the result |
| Role and scope | 10 | The user has confirmed title, scope and dates |
| Role proof | 10 | A named person or document covers the user's role, not only their own account |
| Skeptic answered | 10 | The skeptic question has an answer in Evidence |
| Situation | 5 | The problem and why it mattered then |
| Obstacles | 5 | One specific conversation or decision |
| Lessons | 5 | What the user would repeat or change |
| Tags and uses | 5 | Tags confirmed and at least one approved use |

A partial item gets half its points, rounded down. An empty item gets none.
Quotes and Narrative are not scored. Examples of partial: a Result with no
baseline; result proof that covers the program but not the user's own outcome;
a named person whose coverage has not been asked.

### Bands

| Band | Score | Also requires | Fit for |
|---|---|---|---|
| Starter | 0 to 39 | | Stays in the bank |
| Resume-ready | 40 to 69 | | Resume lines and fit checks, flagged |
| Interview-ready | 70 to 84 | Result filled and the skeptic answered | Interview guides and Job Reels |
| Proven | 85 to 100 | Full result proof and role proof, neither resting on own account or on a named person who has not been contacted | Book chapters, public posts, the top of a Core Reel |

If a card reaches a band's score without the band's requirements, it stays in
the band below and the missing requirement goes first in `strengthen_next`.

The band describes the content. Approval is still separate: a card that is not
approved shows its band with "(draft)", and later steps treat it as a draft.

### Strengthen next

List up to three items that would add the most points, highest first, each
with its points, for example `own outcome figure (+10)`. Put any missing band
requirement first. Recompute the score, band and list whenever the card
changes.

The points shown must be the points the user will get. If answering an item
is likely to add a figure that nothing on file covers, the new figure will
make result proof partial and take points back. List the proof as its own
item, for example `result baseline and period (+10)` and `proof for the new
figure (+8)`. A card held below Proven only because a named person has not
been contacted lists `<name> agrees to confirm (reaches Proven)`.
