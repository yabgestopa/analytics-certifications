# Analytics Certifications

Study repo for three certification tracks, done in order:
1. **SQL** (`1-sql/`): DataCamp SQL Associate (PostgreSQL), HackerRank SQL Basic/Intermediate/Advanced,
   and advanced SQL practice in BigQuery. Goal: SQL proof on the CV for analyst roles.
2. **dbt** (`2-dbt/`): dbt Analytics Engineering Certification (exam version 1.11).
3. **Snowflake** (`3-snowflake/`): trial project + SnowPro Core, later.

Sister project (paused): `../harbour-analytics`.

## Working style

The user is learning by doing. Explain and guide; propose one exercise or concept at a time
and let the user type and run things. Don't bulk-generate queries, models or notes.

## Rules

- **Explain everything like I'm 10.** Every new tool, concept, command or decision gets a
  plain-language explanation with a concrete example or everyday analogy. No unexplained jargon.
  This includes click-through steps in web consoles: explain what each screen, option and
  term means and why we pick it, not just which button to press.
- **Always follow best practice.** When there's a choice, pick the industry best practice,
  say what it is and why in one or two lines, and go with it rather than asking.
- **Exam-first.** Tie every exercise to a competency in the current track's `EXAM_GUIDE.md`.
  Point out exam traps (things that look similar but behave differently, e.g. PostgreSQL vs
  BigQuery syntax, `run` vs `build`). When a competency is practised, update its
  Read / Built / Explain boxes.
- **Use official sources as the truth.** DataCamp's certification pages and the PostgreSQL docs
  for track 1; docs.getdbt.com (v1.11) for track 2; Snowflake docs for track 3. Don't answer
  exam-style questions from memory when the docs can be checked. User dislikes Oracle; don't
  suggest Oracle certifications.
- **Keep the study log, every chat.** `docs/STUDY_LOG.md` gets a dated entry for every chat,
  even short ones: "What we did" + "What I learned" (explain-like-I'm-10, with analogies),
  and update "Coming up next". Write it before the chat ends; don't wait to be asked.
- **Quiz me.** End each topic with 3–5 exam-style questions, and log weak spots in the study log.
- **Push often.** Remind me to commit and push at the end of each session.

## Environment

- GCP project: `harbour-analytics-501211` (shared with the sister project; billing active
  since 2026-11-01, NZ$5/month budget alert). Use separate datasets per track (e.g. `sql_practice`, `dbt_cert`).
- DataCamp exams run in PostgreSQL inside DataCamp's own browser environment.
- dbt Core 1.12 / dbt-bigquery 1.12 on the laptop; the dbt exam targets 1.11.
- `profiles.yml` lives in `~/.dbt/` and is never committed (nor any `*.json` keyfile).
- Commit messages: conventional commits (`feat:`, `docs:`, `chore:`, `test:`).

## Progress

- Current track: **1. SQL**
- Full history: `docs/STUDY_LOG.md`
- Target dates: not set yet. Ask once the user picks a target month for the DataCamp exam.
