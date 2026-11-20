# The Story Bank workbook

An optional spreadsheet view of the bank, for users who want to sort, filter
and scan their stories in one place. The story cards remain the record. The
workbook is built from them.

## When to make it

- Offer it once, at the end of Step 1: "Want your bank as a spreadsheet?"
- Make it whenever the user asks ("give me the spreadsheet", "export my bank").
- If the user keeps one, record `workbook: yes` in `settings.md` and offer to
  refresh it at the end of any step that changed the bank.

Do not make it unasked, and do not make it when the user has said to create no
files.

## How to make it

Use the best option the session has, in this order:

1. A spreadsheet the user can open and keep: a sheet in the Claude app, or an
   `.xlsx` file named `story-bank.xlsx`. With a working folder, save the file
   in `story-bank/`.
2. If the session cannot make a spreadsheet, give each sheet as a table the
   user can paste into one.

Say in one line which option was used.

## Sheets

Put a **Read me** sheet first, holding one line: "Private working file. Check
the Figures to check column before sharing." Then add a sheet only when its
step has been run. Each data sheet has one header row, in row 1, frozen, with
filters on where the tool allows. Store scores as numbers.

### Cards (Step 1)

One row per card, starters included, sorted by score, highest first.

| Column | From |
|---|---|
| Card | id |
| Title | title |
| Role and organization | Role and scope |
| Dates | Role and scope |
| Status | starter, draft or approved |
| Result proof | `result_proof` |
| Role proof | `role_proof` |
| Depth | `depth` |
| Score | `score` |
| Band | `band`, with "(draft)" when the card is not approved |
| Clearance | `clearance` |
| Strengthen next | `strengthen_next`, with points |
| Skill tags | `skill_tags` |
| Job-type tags | `job_type_tags` |
| Approved uses | `approved_uses` |
| Figures to check | any figure marked `not cleared` or `clearance unknown` |
| Related cards | `related_cards` |

### Story Map (Step 2)

A grid. One row per skill, one column for each card on the map. In each cell
where the card shows the skill, write `V+` (result proven and role backed),
`V` (result proven, role on the user's own account) or `U` (no proof). Leave
other cells empty. After the card columns add **Proven cards** (a count of
`V+` and `V`), **Role backed** (a count of `V+`) and **Support** (Well
supported, Supported or Thin). Put the Scope row last, with its label (proven,
partly proven or own account) in the Support column. Put the key to the marks
on the Read me sheet, not under the grid.

### Positions (Step 3)

One row per requirement of each position checked.

| Column | From |
|---|---|
| Company | position record |
| Role | position record |
| Requirement | the posting |
| Must-have or preferred | fit check |
| Rating | Strong, Partial or Gap |
| Cards | card ids behind the rating, with scores |
| Reason | the one-line reason |
| Decision | Apply, Upgrade skills, Hold, Not pursue or undecided |
| Date | date of the decision or the check |

### Open items

One row per open question: the item, where it comes from (a card id, a
position, or the bank settings), and what it blocks. Include each card's
`strengthen_next` items that hold it below the next band.

## Rules

- **Every cell comes from a card, a position record, the map or the settings.** An empty field is an
  empty cell. Do not fill gaps to make the sheet look complete.
- **Words as well as color.** If the tool allows color, shade Band and Rating,
  and keep the word in the cell. Color is never the only signal.
- **The cards win.** When the workbook and the cards disagree, rebuild the
  workbook from the cards.
- **Edits come back as statements.** If the user edits the workbook and asks
  to bring the changes in, treat each edit as something the user has said:
  update the card, apply the shared rules, and re-score. A score or band typed
  into the workbook is ignored. Scores are computed. If an edit conflicts with
  what the card says, hold it and ask. Do not rebuild the workbook, which
  would erase the edit, until the user has answered.
- **It is a private working file.** The workbook may hold figures of any
  clearance, because it is part of the bank. If the user says they will share
  it, make a share copy with every figure that is not cleared removed, and
  list figures with clearance unknown under "Confirm before sending".
