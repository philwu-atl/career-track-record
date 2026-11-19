# The story session

A guided pass on one story card. The user reacts to a draft rather than
telling the story from scratch. The card's depth sets how many questions are
asked and when to stop. The accuracy rules never change with depth.

## Depth

| Depth | When to suggest it | Question cap | Stop when the score reaches | About |
|---|---|---|---|---|
| Quick | Exploring, networking, background cards | 4 | 40 | 5 minutes |
| Standard | Applying to a role (the default) | 7 | 70 | 10 minutes |
| Deep | Interview booked, executive roles, book chapters | 10 | 85 | 15 minutes |

The depth is set in Step 1 (see the skill). The user can change it at any
point: "go deeper" moves the card up one level and raises the cap and target;
"park it" ends the session at once and goes to the close (section 4).

## How to ask

- **One ask per turn.** Each turn asks one thing and waits. A short yes-or-no
  confirmation may ride along ("I've spelled it Philippe; say if that's
  wrong"). Do not ask multi-part questions.
- **Most points first.** Ask about the empty or partial item worth the most
  points (see the card template), in this order: Result, Actions (you versus
  the team), Evidence (result proof and role proof in one question), Role and
  scope, the skeptic question, then Situation, Obstacles, Lessons.
- **Stop at the target or the cap.** Stop asking when the card reaches the
  depth's target score and its band requirements are met, or when the cap is
  spent, whichever comes first. Go to the close. Empty fields stay empty and go
  into `strengthen_next`.
- **Never ask again** about something the user has already confirmed.

### What counts against the cap

Count every question Claude chooses to ask, including the read-back
confirmation in section 1 and the challenge questions. Do not count:

- the closing approval question, which is always asked;
- spellings, typos and small corrections. Fix them in the read-back and state
  the assumption instead of asking;
- anything the user asks for: a web search, suggested quotes, a re-read. When
  a search the user asked for needs their confirmation, let it ride along with
  the next question.

### Answers that are not complete

- **"I don't know."** Do not follow up. Leave the field as it is, add it to
  `strengthen_next` if it carries points, and move on.
- **A partial answer** (the user answers part of the question and ignores or
  does not know the rest). Record what was answered and mark the field
  partial. At Quick and Standard, do not follow up; the missing part goes to
  `strengthen_next`. At Deep, one follow-up on that field is allowed, and it
  counts against the cap.
- **A vague answer.** At Deep, one follow-up from the table below. At Quick
  and Standard, record it as partial and move on.

Do not list open items during the session. They are reported once, at the
close.

## 1. Show the draft (counts as one question)

Present the card with its empty and partial fields marked. Ask the user to
correct anything wrong and to confirm the Role and scope line (title, team
size, sites, budget), because other steps rely on it.

## 2. Fill the gaps

Ask in points order, one item per turn.

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

Ask once per figure whether it is public or cleared for use, and only for
figures the user supplied. A figure taken from a public source that the user
confirmed is recorded as `cleared (public source)` without a question. A
figure that appears on several cards is asked about once and the answer
carried to the other cards. A clearance question counts against the cap.

A web search during the session is allowed when the user asks for one. Show
the source, record it in Evidence once the user confirms it, and say what it
covers.

If the user asks Claude to suggest quotes, draft them only from facts already
on the card, label them as drafts, and record one only if the user picks it
(see the card template).

## 3. Challenge

Two tough questions a senior interviewer would ask.

1. **"What share of this was you versus the team?"** This is part of the
   Actions question above. Asked at every depth. Skip it only when the user
   has already given the split in this session. Reword the title and actions
   to match the answer.
2. **"What would a skeptic say about that number?"** If the card has no
   number of the user's own, ask "What would a skeptic doubt about this
   story?" Asked at Standard and Deep. At Quick, ask it only if the cap
   allows; otherwise it goes into `strengthen_next`. Record the answer in
   **Evidence**.

If an answer weakens a claim, rewrite the claim to the weaker, accurate
version.

## 4. Close: approve, validate, score

Read the finished card back, with the proposed skill and job-type tags in it.
Then ask one closing question: approve the card as read back, and which uses
it may have (resume, interview, post, book).

- **Approval.** If the user approves, set status to `approved`. Approving the
  read-back confirms the tags shown unless the user changes them. If they do
  not approve, or are not sure, leave it as `draft` and say what is holding it
  up. If they name no uses, leave approved uses empty.
- **Proof.** Apply the validation rule in the skill. Fill `result_proof` and
  `role_proof`. Set `proof` to `validated` when the result is backed by a
  document, a confirmed public source or a named person. Otherwise set
  `unvalidated` and say what is missing.
- **Score.** Compute the score and band and write `strengthen_next` (see the
  card template). Tell the user in one line, for example: "Card 08: 57,
  Resume-ready. To reach Interview-ready: your own outcome figure (+10), an
  answer for a skeptic (+10)."

Then report the open items once, in a short list.

## Strengthen session

When the user comes back to a card ("strengthen card 08", or from a gap check
in Step 3), ask only the items in `strengthen_next`, highest first, under the
card's depth cap or a higher depth if the user chooses one. Do not re-run the
whole session. Re-score at the end and update `strengthen_next`.

The user may also answer open items by text or voice memo between sessions.
Add the answers to the card and re-score it.
