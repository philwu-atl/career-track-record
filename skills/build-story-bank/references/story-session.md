# The story session

A guided pass of about 15 minutes per story. The user reacts to a draft rather
than telling the story from scratch. Ask one question at a time and wait for
the answer.

Aim for about 10 questions. Ask only about fields that are empty or partial,
and never ask again about something the user has already confirmed. Combine
questions where it is natural, such as tags with approval. Use a follow-up only
when an answer is vague. If the user says they do not know, do not follow up:
leave the field empty, note it as an open question, and move on. If the user
answers part of a question and does not know the rest, that is final: do not
ask for the rest again.

## 1. Show the draft (1 minute)

Present the card with its empty and partial fields marked. Ask the user to
correct anything wrong in the filled fields. Ask them to confirm the Role and
scope line (title, team size, sites, budget), because other steps rely on it.

## 2. Fill the gaps (8 to 10 minutes)

Ask one question for each field that is empty or partial, in this order.

| Field | Question | Follow-up if the answer is vague |
|---|---|---|
| Result | What changed, measured how, from what baseline, over what period? | If you had to defend the number to a CFO, what would you show? |
| Role and scope | Ask only for the parts still missing after step 1 (for example budget or P&L). | Who did you need approval from? |
| Situation | What was the problem, and why did it matter then? | What would have happened if nothing was done? |
| Actions | What did you personally do that made the difference? | What would not have happened if you had been absent? |
| Obstacles | What was the hardest part, and what did you do about it? | Give one specific conversation or decision. |
| Evidence | Who could back this up, and is there a document or number you could point to? For each person named, also ask what they can confirm (the result, your role, or both), unless the answer already says. | A former boss, a customer, a board deck? |
| Lessons | What would you repeat, and what would you do differently? | How did you apply this later? |
| Quotes (optional) | Is there a line someone said that you would repeat in an interview? | None. Skip if nothing comes to mind. |

Ask once per figure whether it is public or cleared for use. Record `cleared`,
`not cleared` or `clearance unknown`. A figure that appears on several cards,
such as a budget on the Role and scope line, is asked about once and the answer
carried to the other cards.

## 3. Challenge (2 minutes)

Two tough questions a senior interviewer would ask are part of every session.
They take priority over the rule against repeating questions.

1. "What share of this was you versus the team?" Skip it only when the user
   has already given that split in this session; then record it as answered.
   Record the answer in **Actions**, and reword the title and actions to match
   it.
2. "What would a skeptic say about that number?" If the card has no number,
   ask "What would a skeptic doubt about this story?" Record the answer in
   **Evidence**.

If an answer weakens a claim, rewrite the claim to the weaker, accurate
version.

## 4. Approve and validate (1 minute)

Read the finished card back. Propose skill and job-type tags and ask the user
to confirm them. Then:

- **Approval.** Ask the user to approve the card and say which uses they
  allow: resume, interview, post, book. If they approve, set status to
  `approved`. If they do not, or are not sure, leave it as `draft` and say what
  is holding it up. If they name no uses, leave approved uses empty.
- **Proof.** Apply the validation rule. Set proof to `validated` when the
  result is backed by a document, a confirmed public source, or a named person.
  Record what each source covers. If the user's role rests on their own
  account, write "role: own account". Otherwise set `unvalidated` and say what
  proof is missing.

Approval and proof are separate. Record both.

## Between sessions

The user may answer open questions later by text or voice memo. Add the answers
to the card and update its completeness count.
