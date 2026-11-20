# The story session

A guided pass on one story card. The user reacts to a draft instead of telling
the story from scratch. The card's depth sets how many questions are asked and
when to stop. The validation level sets whether proof is asked about. The
accuracy rules never change.

## Depth, level and when to stop

| Depth | When to suggest it | Question cap | About |
|---|---|---|---|
| Quick | Exploring, networking, background cards | 4 | 5 minutes |
| Standard | Applying to a role (the default) | 7 | 10 minutes |
| Deep | Interview booked, executive roles, book chapters | 10 | 15 minutes |

Stop asking when the card reaches the target score below and meets what its
band requires, or when the cap is spent, whichever comes first.

| Depth | Target when proof is not being asked | Target when proof is being asked |
|---|---|---|
| Quick | 40 | 40 |
| Standard | 55 | 70 |
| Deep | 65 | 85 |

Proof is being asked on a card when the validation level is "check
everything", or when it is "check the key stories" and the card is a key
story. Otherwise it is not, and the lower target applies, because a card with
no proof and no skeptic answer cannot score above 65.

The user can change things at any point: "go deeper" moves the card up one
depth; "park it" ends the session at once and goes to the close.

## What to ask about

Ask about the empty or partial item worth the most points, one item per turn.

- **When proof is not being asked:** Result, Actions (you versus the team),
  Role and scope, then Situation, Obstacles, Lessons. Do not ask the Evidence
  question, the skeptic question or a clearance question. Those items go to
  `strengthen_next`.
- **When proof is being asked:** Result, Actions, Evidence (result proof and
  role proof in one question), Role and scope, the skeptic question, then
  Situation, Obstacles, Lessons.

At every level, record proof that the documents show or that the user
volunteers. Never turn proof away.

**Never ask again** about something the user has already confirmed.

## How the session looks

- **Progress line.** Start every question turn with one line, and put it
  first in the reply:
  `Card 08 · question 3 of up to 7 · score 45, target 55`.
  On the closing turn use `Card 08 · close · 3 of up to 7 asked · score 57`.
- **Card view, not the template.** Show the card in the card view defined in
  the card template, never as the raw template with its header block. Draw it
  as a visual when the session can. Show the card at the draft and at the
  close only. Do not draw a visual on a question turn.
- **Full text on request.** "Show full card" gives the card in the template
  format at any point.

Fixed-choice questions in a session:

| Question | Choices |
|---|---|
| Which of two conflicting figures is right | one choice per figure · Neither |
| Figures on this card (asked at the close) | All fine to share · Some are not · Not sure |
| Closing approval | Approve · Not yet · Park it |
| Approved uses (pick any) | Resume · Interview · Post · Book |
| Change of depth | Quick · Standard · Deep |

Every other question is open. Ask it in plain words and let the user type or
dictate the answer.

### What counts against the cap

Count every question Claude chooses to ask, including the draft check and the
challenge questions. Do not count:

- the closing question, which is always asked;
- spellings, typos and small corrections. Fix them and state the assumption;
- anything the user asks for: a web search, suggested quotes, a re-read.

### Answers that are not complete

- **"I don't know."** Do not follow up. Leave the field as it is, add it to
  `strengthen_next` if it carries points, and move on.
- **A partial answer.** Record what was answered and mark the field partial.
  At Quick and Standard, do not follow up. At Deep, one follow-up on that
  field is allowed, and it counts against the cap.
- **A vague answer.** At Deep, one follow-up from the table below. At Quick
  and Standard, record it as partial and move on.

Do not list open items during the session. They are reported once, at the
close.

## 1. Show the draft

Show the card in the card view, with its empty and partial fields marked.

If the documents disagree about a fact on this card, ask about that first, as
its own question, before anything else. It counts against the cap.

Then ask the draft check in plain words, as one question: is anything on the
card wrong, including the Role and scope line? Tell the user to reply "ok" or
say what to fix. Do not use tappable choices for the draft check. It counts as
one question.

## 2. Fill the gaps

| Item | Question | Follow-up (Deep only) |
|---|---|---|
| Result | What changed, measured how, from what baseline, over what period? | If you had to defend the number to a CFO, what would you show? |
| Actions | What did you personally do, and what share was you versus the team? | What would not have happened if you had been absent? |
| Evidence | Who or what could back this up, and would they confirm the result, your role, or both? | A former boss, a customer, a board deck? |
| Role and scope | Ask only for the parts still missing after section 1. | Who did you need approval from? |
| Situation | What was the problem, and why did it matter then? | What would have happened if nothing was done? |
| Obstacles | What was the hardest part, and what did you do about it? | Give one specific conversation or decision. |
| Lessons | What would you repeat, and what would you do differently? | How did you apply this later? |
| Quotes | Offer only at Deep, last, and only if the cap allows: "Is there a line you would repeat in an interview?" | None. |

"What share was you versus the team" is part of the Actions question and is
asked at every depth and level. Skip it only when the user has already given
the split. A split stated in words ("the design was mine; supervisors ran the
checks") is enough for full points. A share figure is not required.

When the user names a person as proof, record them as "named person, not
contacted" unless the user says the person has agreed to confirm. Ask what the
person can confirm only if the user has not said.

A web search during the session is allowed when the user asks for one. Show
the source, record it in Evidence once the user confirms it, and say what it
covers.

If the user asks Claude to suggest quotes, draft them only from facts already
on the card, label them as drafts, and record one only if the user picks it.

## 3. The skeptic question

Asked only when proof is being asked on this card, at Standard and Deep. At
Quick, ask it only if the cap allows.

"What would a skeptic say about that number?" If the card has no number of the
user's own, ask "What would a skeptic doubt about this story?" Record the
answer in Evidence.

If an answer weakens a claim, rewrite the claim to the weaker, accurate
version. If the you-versus-team answer changes the user's part, change the
title's wording to match, and keep the result first.

## 4. Close

Do not read the whole card back. The user checked the draft in section 1, so
show what changed since then: one or two lines for each changed field, then
the proposed skill and job-type tags. If more than half the content fields
changed, show the whole card view instead.

Then ask one closing question. It may hold up to three parts, shown together:

1. approve the card as shown;
2. which uses it may have (resume, interview, post, book), only if no uses
   are set yet;
3. the figures question, only when proof is being asked on this card, the
   card holds employer or client figures, and its clearance is not yet
   recorded.

After the answer:

- **Approval.** If the user approves, set status to `approved`. Approving
  confirms the tags shown unless the user changes them. If they do not
  approve, leave it as `draft` and say what is holding it up.
- **Proof.** Apply the validation rule in the shared rules. Fill
  `result_proof` and `role_proof` with the labels given there.
- **Score.** Compute the score and band and write `strengthen_next`. Show the
  card header from the card view. If an answer moved more than one line of the
  score, say so plainly, for example: "Result +10. Result proof −8, because
  nothing on file covers the new figure. Net +2."
- **Save.** With a working folder, the card file is already saved as answers
  came in; clear `pending_changes` and say where the file is. Do not print the
  card. With no folder, give the full card once, in the template format inside
  a code block.

Then report the open items once, in a short list, and follow the handoff rule:
say what comes next and let the user choose.

## Strengthen session

When the user comes back to a card ("strengthen card 08", or from Step 3 or
Step 4):

1. Show the card header first, so the user sees the card before any question.
2. Ask only the items in `strengthen_next`, most points first. When points
   tie, ask whatever the next band requires first, then follow the order
   Result, Actions, Evidence, Role and scope, skeptic, Situation, Obstacles,
   Lessons.
3. Ask them even if the card is already past its target, and whatever the
   validation level is. The user asked for this.
4. The cap starts again at 1 for this session. Stop when the items are done,
   the cap is spent, or the user says stop.
5. If an answer brings a new figure with no proof behind it, do not ask a
   proof question for it. Record it, and put "proof for <the figure>" in
   `strengthen_next`.
6. At the close, show what changed and ask only to approve the changes. Do
   not ask again for uses that are already set.
7. Re-score and update `strengthen_next`. Say the net change in points.

Do not re-run the whole session. The user may also answer open items by text
or voice memo between sessions. Add the answers to the card and re-score it.
