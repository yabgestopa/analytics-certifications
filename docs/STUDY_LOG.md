# Study Log: dbt Certification Prep

What I did and learned in each session, written so a 10-year-old could follow it.
Newest entries at the bottom. Every chat gets an entry.

> The big picture: the exam checks that I can **build** dbt models, **protect** them
> (governance), **fix** them when they break (debugging), **check** them (tests), **connect**
> them to the outside world (exposures, freshness), and **work smart** (state: only rebuild
> what changed). This repo is the practice car park. harbour-analytics is the real road trip.

---

## Session 1 — 1 November 2026: Setting up the study repo

**What we did**
- Paused harbour-analytics at a clean point (last commit `ed3ba0f`) so nothing was left unpushed.
- Created this repo, `dbt-certification`, in a separate folder next to harbour-analytics.
- Read the official exam page and turned its 7 topics into a checklist (`docs/EXAM_GUIDE.md`).
- Set up `CLAUDE.md` with the study rules, and this log.

**What I learned**
- **Why a separate repo?** Practice work and portfolio work have different jobs. Like a
  practice car park vs a road trip: you can stall, crash into cones and try again in the car
  park without it showing up on the trip.
- **Why not put it inside harbour-analytics?** A Git repo inside another Git repo confuses Git,
  like putting one diary inside another diary's pages. Separate folders side by side keep them clean.
- **Why Jaffle Shop data, not Xero?** Jaffle Shop is dbt's official made-up café (customers,
  orders, payments), and dbt's own docs and courses use it, so examples will match. Also,
  some exam topics need data I can change and re-run. A **snapshot** records how a row
  changes over time, like a height chart on a door frame, so I need to be able to change the
  "height". An **incremental model** adds only new rows instead of rebuilding everything,
  like adding today's diary entry instead of rewriting the whole diary, so new rows need to arrive.
- **The exam is version 1.11.** My laptop has dbt 1.12, which is newer and includes
  everything in 1.11. It's like studying for a driving test in a newer model of the same car.
- **The 7 exam topics** (see `docs/EXAM_GUIDE.md`): developing models, governance, debugging
  models, troubleshooting pipelines, tests, external dependencies, and state.
- **Read → Built → Explain.** Each competency is only done when I can explain it simply.

---

## Coming up next
1. Open the exam page in a browser and fill in the question count, time, pass mark and price
   in `EXAM_GUIDE.md`. Pick a target exam month.
2. Try the 10 sample questions on the exam page cold, as a starting baseline.
3. Create the GitHub repo and push (needs my OK).
4. Fix the Google login (`gcloud auth application-default login`), then build the setup
   by hand: venv, `dbt init`, a `dbt_cert` dataset in BigQuery, and load Jaffle Shop as seeds.
5. Start topic 1: materializations.
