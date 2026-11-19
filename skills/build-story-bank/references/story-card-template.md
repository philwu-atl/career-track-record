# Story card template

One file per story. Keep the header fields exactly as named so later steps can
read them.

```markdown
---
id: 01
title: <one line, result first>
status: starter | draft | approved
proof: validated | unvalidated
complete: <fields filled> of 12
skill_tags: [<skill>, <skill>]
job_type_tags: [<job type>, <job type>]
approved_uses: []
---

## Role and scope
Title, organization, team size, budget or P&L, dates.

## Situation
The business problem, in two sentences.

## Actions
What the user personally did, up to five things. Mark anything the team did.
One or two accurate actions are better than three padded ones.

## Obstacles
What made it hard. One specific conversation or decision.

## Result
The measured outcome, with the baseline and the time period.

## Evidence
Where the proof comes from: a document, a public source found by search, or a
named person who can back it up. Say what each source covers (the result, the
user's role, the scope). For a named person, say what they can confirm. If the
user's role rests on their own account, write "role: own account". Note whether
figures are public, cleared, or "clearance unknown".

## Lessons
What the user would repeat or change.

## Quotes
Word-for-word lines usable in an interview.

## Narrative (optional)
A longer telling, for a book chapter or a post.
```

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

Propose skill and job-type tags, then ask the user to confirm them.

## Completeness

Count the filled fields out of twelve, using these rules:

- A field is **filled** when it holds the user's answer and nothing essential
  is missing.
- A field is **partial** when part is missing, such as a Result with no
  baseline or period. Name what is missing. Count partial as not filled.
- An Evidence field that says there is no proof is **empty**.
- Tag fields count once the user has confirmed them. If the user confirms some
  proposed tags and not others, keep the confirmed ones, drop the rest, and
  count the field as filled.

A card with an empty Result or Evidence field is not ready to validate,
whatever its count. It can still be approved, because approval means the
content is accurate, not that it is proven.
