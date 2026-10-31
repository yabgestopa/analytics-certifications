# Study Log: Analytics Certifications

What I did and learned in each session, written so a 10-year-old could follow it.
Newest entries at the bottom. Every chat gets an entry.

> The big picture: **SQL** first (the language every data job uses), then **dbt** (the tool
> analytics engineers use to organise that SQL), then **Snowflake** (the warehouse Auckland
> employers ask for most). This repo is the practice car park. harbour-analytics is the real road trip.

---

## Session 1 — 1 November 2026: Choosing the path and setting up the study repo

**What we did**
- Paused harbour-analytics at a clean point so nothing was left unpushed.
- Started a dbt study repo and turned the official dbt exam page into a checklist.
- Changed course: decided to get a **SQL certificate first**, so my CV shows progress if I
  apply for another analyst role before moving fully into analytics engineering.
- Compared SQL certificates and searched Auckland job ads. Picked the path:
  HackerRank SQL (free) → DataCamp SQL Associate → dbt certification → Snowflake.
- Renamed the repo to `analytics-certifications` with one folder per track, and turned the
  official DataCamp SQL Associate requirements into a checklist (`1-sql/EXAM_GUIDE.md`).
- Published it as a **public** repo: https://github.com/yabgestopa/analytics-certifications.
  Public because it's linked from my CV, and the `.gitignore` keeps secrets out.

**What I learned**
- **A certificate isn't the same as proficiency.** A certificate is a driving licence: proof
  you passed a test on one day. Being a good driver comes from hours behind the wheel. For SQL,
  that means writing lots of queries on real data. Interviewers usually test SQL live.
- **SQL certificates compared:**
  - *Oracle 1Z0-071*: well known and proctored, but ~US$245 and Oracle's own SQL flavour. Not for me.
  - *Google Cloud Associate Data Practitioner*: Google's entry data certificate. More about
    Google's products than SQL, and BigQuery is rare in Auckland ads.
  - *DataCamp SQL Associate*: included in a ~US$14–25/month subscription, with a practical
    exam on a real business problem. ✅ Chosen.
  - *HackerRank SQL*: free, quick, good for a fast CV line. ✅ Doing alongside.
- **What transfers between warehouses?** The *ideas* (warehouses, tables, partitioning,
  permissions, loading data) transfer between BigQuery, Snowflake and Databricks. The
  *product names and buttons* don't. Like learning to drive in a Toyota and then driving a
  Honda. About 90% of SQL is the same everywhere. Only small things like date functions differ.
- **Auckland job ads lean Snowflake**, usually with dbt. Databricks and Microsoft Fabric
  show up too, and BigQuery barely appears. So: practise SQL where it's free (BigQuery) and
  pick a *platform* certificate (SnowPro) later.
- **Why learn in BigQuery if jobs use Snowflake?** Learning SQL is like learning to cook:
  chopping and frying are the same in any kitchen. I already have a free kitchen with food in it.
  Snowflake has no permanent free tier.
- **DataCamp's exam uses PostgreSQL**, a third SQL flavour. Same ideas again, different
  spelling. For example, the median in PostgreSQL is
  `percentile_cont(0.5) within group (order by x)`.
- **The DataCamp practical is all-or-nothing.** Every part must be right to pass, so
  checking my own answers carefully is a skill to practise, not just writing queries.
- **It includes statistics in SQL:** mean, median, mode (the middle and the most common),
  range, standard deviation and variance (how spread out values are), skewness (whether the
  data leans to one side, like a slide), and missingness (how many blanks, and whether they
  distort the answer).
- **One repo, three folders**, done in order: like a school timetable with subjects in the
  order you take them. Nothing was on GitHub yet, so renaming cost nothing.

---

## Coming up next
1. HackerRank **SQL (Basic)**: a free, quick first certificate.
2. Start DataCamp Premium and the **SQL Fundamentals** track (26 hours). Pick a target month
   for the exam, remembering there are only 30 days from registering to finish both parts.
3. Try DataCamp's readiness quiz and sample practical early, as a baseline.
4. Alongside: window functions in BigQuery (see the Advanced SQL table in `1-sql/EXAM_GUIDE.md`).
5. Later: dbt (`2-dbt/`), then Snowflake (`3-snowflake/`).
