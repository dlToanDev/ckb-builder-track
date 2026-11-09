# Weekly Learning Reports

Write one report per actual learning week using [week-01.md](week-01.md) as the
unfilled template. Reports describe the author's real work, including incomplete
attempts and blockers. Repository scaffolding is not completed learning.

## Programme reference

The [CKBuilder Handbook](https://docs.google.com/document/d/1aFHXU1ZL1MyIbBAIVRjG6stqdWwPUPyHV90O1QNwY-M/edit?usp=sharing)
is linked by the programme organizer in the
[official Catalyst report](https://talk.nervos.org/t/nervos-community-catalyst-quarterly-reports/8822).
That report confirms weekly reporting. During setup, the Handbook page exposed
only its title and a JavaScript notice; its body could not be independently read.
The structure below follows the repository owner's supplied requirements. Confirm
the latest Handbook wording and any submission channel with the programme before
claiming formal compliance.

Plan for at least **4–5 hours of study per week**, as specified in the supplied
Handbook requirements. Record the actual total even when it is below that target.
Do not inflate hours or treat planned hours as time already spent.

## Maintain a consistent schedule

1. Choose a fixed seven-day reporting period and one weekly publication deadline.
   Suggested schedule: Monday–Sunday, publish Sunday by 20:00 in
   `Asia/Ho_Chi_Minh` (UTC+07:00). Adopt a different schedule if the programme specifies one.
2. At the start of the week, copy the template to `week-NN.md`, change its title,
   clear all previous personal content, and fill in dates and planned objectives.
   Preserve the original Week 1 file until its actual reporting week begins.
3. Log study sessions as they happen: date, start/end times, breaks, focused minutes,
   activity, and evidence. Do not count overlapping sessions twice.
4. Sum focused minutes, divide by 60, and enter the result under total study hours.
   Exclude breaks and unattended downloads or builds. Use honest estimates only
   when necessary and label how the estimate was obtained.
5. Record topics, attempts, results, challenges, takeaways, and next steps in your
   own words. Leave unfinished work explicitly incomplete.
6. Review evidence and redact sensitive information before publishing. Update the
   root README report index and roadmap only to match verified progress.
7. Review the diff and request owner approval before committing or pushing.
   Publishing the report means making its reviewed changes available on GitHub;
   any additional programme submission must follow the confirmed Handbook process.

## Required report sections

Each report contains the reporting period, total study hours, learning objectives,
topics studied, practical exercises, evidence of progress, challenges encountered,
key takeaways, and plans for the following week. Keep the activity log so that the
hours can be reconciled with the narrative.

## Attach evidence

- Save genuine screenshots under `screenshots/` using names such as
  `week-01-cell-diagram.png`. From a report, the relative path would be
  `../screenshots/week-01-cell-diagram.png`. Add a Markdown image only after the
  file exists; include a useful caption and capture date.
- Link a real published commit using
  `https://github.com/dlToanDev/ckb-builder-track/commit/` followed by its actual
  full hash. Do not insert a sample hash or imply an unpublished commit is remotely accessible.
- For devnet transactions, record the actual transaction hash, network/RPC,
  observed status, and sanitized local query output. Public explorers do not show
  a local OffCKB chain. Note any devnet reset that makes old evidence unreproducible.
- For testnet transactions, record the real hash and verified explorer link only
  after submission and confirmation. Include the checked output Cell or asset ID.
- For tests, preserve the command, tool versions, observed output, and date. A
  checklist or expected result alone is not execution evidence.

Never include private keys, recovery phrases, access tokens, full environment files,
or account commands that reveal secrets in screenshots or terminal transcripts.

## Publish weekly, not in batches

Weekly publication makes progress reviewable while blockers and observations are
fresh, supports timely feedback, and preserves an accurate timeline. Generating
several retrospective reports at once obscures that timeline. If a report is late,
label the actual publication date and explain the gap honestly; do not backdate it.
If no study took place, report that fact with actual hours and a revised plan.

## Responsible AI assistance

The author supplies the experiences, hours, evidence, and reflections. AI may improve
grammar or organization of those facts. It must not generate fictional activities,
personal takeaways, tests, transactions, screenshots, or achievements. Review every
AI-edited sentence against the underlying evidence before publishing.
