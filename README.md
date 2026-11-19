# Career Track Record

Bank your career stories with proof. Check any job against them.

A four-step Claude plugin that captures and sharpens your career stories, then
validates each one against a document, a public source, or a named person, so
you can prepare for job opportunities, write a book or bio, and tell your
story.

Built with Claude. This is an independent project and is not affiliated with or
endorsed by Anthropic.

![The four steps](docs/four-steps.png)

## Who it is for

People with a long career and thin records of what they did. If you have
twenty years of work and a two-page resume, most of your evidence lives in your
head. This workflow gets it out, checks it, and keeps it in one place.

## The four steps

| Step | Skill | What it does | What you get |
|---|---|---|---|
| 1 | `build-story-bank` | Loads your resumes, bios and other documents, drafts story cards, and fills the gaps in a short guided session per story (5 to 15 minutes, depending on depth) | A bank of story cards, each with proof and a strength score |
| 2 | `build-story-map` | Links every story to the skills it proves, the job types it fits and the proof behind it | A story map (an ontology), target job types, a Core Reel |
| 3 | `check-a-position` | Scores a posting against your bank, finds the gaps, and closes them by capturing a story you already have or planning training | A fit check, new or updated stories, a decision |
| 4 | `cut-highlight-reel` | Picks the 5 to 7 stories for one job and builds from them | Resume changes, an interview guide, a debrief |

Steps 3 and 4 repeat for every position. The bank and the map get stronger each
time.

![Step 3 in detail](docs/step-3-feedback-loop.png)

## Three rules the workflow follows

1. **It never invents experience.** Every line traces to a story card. If the
   bank cannot support a claim, the claim is left out.
2. **A story needs proof.** A card is validated only with a document, a public
   source you confirm, or a named person who can back it up.
3. **The fit check is honest.** It states weaknesses as plainly as strengths.

In practice this tends to make a resume more accurate, not more inflated:
"built" becomes "helped build" when that is what happened.

## Depth and score

Not every story needs the same work. A story you might mention while
networking needs less than one you will tell in a final-round interview.

- **Depth.** Each story gets a session sized to its use: Quick (up to 4
  questions), Standard (up to 7) or Deep (up to 10). Claude suggests a depth
  from where you are in your search, and you can change it. Claude asks the
  questions that matter most first and stops when the story is strong enough
  for its use. Depth changes how much is asked, never the accuracy rules.
- **Score.** Each story gets a strength score from 0 to 100 and a band:
  Starter, Resume-ready, Interview-ready or Proven. Every story also lists the
  two or three things that would raise its score most, with the points each
  is worth. Come back in any session, say "strengthen card 08", and Claude asks
  only those.

When you check a job, any story that backs a key requirement but scores below
Interview-ready is flagged, with an offer to strengthen it.

## Install

This is a standard Claude plugin: a manifest in `.claude-plugin/plugin.json`
and four skills under `skills/`.

- **Claude Code:** clone this repository and start Claude Code with
  `claude --plugin-dir ./career-track-record`.
- **Claude apps:** see Anthropic's plugin documentation for adding a plugin:
  https://code.claude.com/docs/en/plugins

## Use

Start a conversation and say what you want in plain words:

- "Build my story bank." Then share your resume and other documents.
- "Build my story map."
- "Check this job." Then paste the posting.
- "Cut a highlight reel for this job."

## Your data

- **The plugin has no server and collects nothing.** It is a set of
  instructions for Claude. Nothing you enter is sent to the author or to any
  third party by this plugin.
- **Your story bank stays with you.** It is saved as plain text files in the
  folder you work in with Claude:

  ```
  story-bank/
  ├── settings.md    your target job types and default depth
  ├── cards/         one file per story card
  ├── story-map.md
  ├── positions/     one file per position checked
  └── reels/         highlight reels
  ```

  If you use Claude without a working folder, your stories stay in your
  conversation and you save them yourself.
- **Claude still processes what you share.** As with anything you do in
  Claude, your documents and answers are handled under your own Claude plan
  and privacy settings. This plugin does not change that.
- **Confidential figures are tracked.** Career stories often contain employer
  or client figures. The plugin asks whether each figure is cleared for use. A
  figure marked not cleared is kept out of every resume, guide and post.

## Using AI in job applications

Check each employer's policy on using AI in applications. This workflow is
built for the common rule: your experience and your first draft are your own,
and AI helps you find, check and sharpen them.

## Status

Version 0.1.4. The author built this and uses it for his own job search. It has
been through three simulated test runs and one run on a real career, and has
not yet been tested by many people. Feedback and corrections are welcome
through Issues.

## License

MIT. See [LICENSE](LICENSE).
