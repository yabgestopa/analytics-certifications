# dbt Certification Prep

Study repo for the **dbt Analytics Engineering Certification** (exam version 1.11).
Hands-on practice with dbt Core + BigQuery using dbt's Jaffle Shop sample data.
Sister project (paused): `../harbour-analytics`.

## Working style

The user is learning by doing. Explain and guide; propose one file or concept at a time and
let the user type and run things. Don't bulk-generate models or notes.

## Rules

- **Explain everything like I'm 10.** Every new tool, concept, command or decision gets a
  plain-language explanation with a concrete example or everyday analogy. No unexplained jargon.
  This includes click-through steps in web consoles: explain what each screen, option and
  term means and why we pick it, not just which button to press.
- **Always follow best practice.** When there's a choice, pick the industry best practice,
  say what it is and why in one or two lines, and go with it rather than asking.
- **Exam-first.** Tie every exercise to a competency in `docs/EXAM_GUIDE.md`. Point out exam
  traps (things that look similar but behave differently, like `run` vs `build`). When a
  competency is practised, update its Read / Built / Explain boxes.
- **Use the official docs as the source of truth** (docs.getdbt.com, exam version 1.11).
  Don't answer exam-style questions from memory when the docs can be checked. Say when
  something is dbt Cloud-only vs dbt Core.
- **Keep the study log, every chat.** `docs/STUDY_LOG.md` gets a dated entry for every chat,
  even short ones: "What we did" + "What I learned" (explain-like-I'm-10, with analogies),
  and update "Coming up next". Write it before the chat ends; don't wait to be asked.
- **Quiz me.** End each topic with 3–5 exam-style questions (multiple choice, like the real
  exam), and log weak spots in the study log.
- **Push often.** Remind me to commit and push at the end of each session.

## Environment

- GCP project: `harbour-analytics-501211` (shared with the sister project; billing active
  since 2026-11-01, NZ$5/month budget alert). This repo uses its own dataset: `dbt_cert`.
- dbt Core 1.12 / dbt-bigquery 1.12 on the laptop; the exam targets 1.11
- `profiles.yml` lives in `~/.dbt/` and is never committed (nor any `*.json` keyfile)
- Commit messages: conventional commits (`feat:`, `docs:`, `chore:`, `test:`)

## Progress

- Exam topics checklist: `docs/EXAM_GUIDE.md`
- Full history: `docs/STUDY_LOG.md`
- Exam date: not set yet. Ask once a target month is chosen.
