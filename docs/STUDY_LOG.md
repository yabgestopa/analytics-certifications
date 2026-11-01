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

## Session 2 — 1 November 2026: My first SQL query (starting from zero)

**What we did**
- Restarted SQL from zero: one concept per step, no shortcuts.
- Set up Claude in Chrome so Claude can see my BigQuery tab (I type, Claude looks when I say "check").
- Lesson 1: what a database, table, column and row are. Looked at the Shakespeare public table
  (`bigquery-public-data.samples.shakespeare`): 4 columns: `word`, `word_count`, `corpus`, `corpus_date`.
- Lesson 2: wrote and ran my first query, `SELECT word, corpus FROM ...`. Got 164,656 rows.

**What I learned**
- **A database is a filing cabinet, and each table is a drawer.** Columns are the kinds of information.
  Rows are the things. In the Shakespeare table, one row = one word inside one play
  ("*love* appears 87 times in *Hamlet*"). Always check what one row means first.
- **`FROM` = which drawer. `SELECT` = which columns to show.** Commas between columns, no comma
  after the last one. `SELECT *` = every column.
- **The validator is SQL spell-check.** A green tick means the query makes sense. It also shows how
  much data the query will read, like a taxi meter.
- **BigQuery stores data by column (columnar storage)**, like one drawer per column. `word, corpus`
  read 3.62 MB, but `*` read 6.13 MB, because you pay for every drawer you open. Best practice: name
  only the columns you need.
- **Trap:** PostgreSQL (the DataCamp exam) stores by row, so `SELECT *` there is about clarity, not cost.
  BigQuery puts table names in backticks; PostgreSQL doesn't.

- **Lesson 3: `WHERE` is a sieve.** It keeps only rows that pass a test. It goes after `FROM`.
  Text goes in single quotes (`'hamlet'`), numbers don't. `WHERE corpus = 'hamlet'` gave 5,318 rows.
  `WHERE word_count > 100` gave 1,333 rows, mostly "glue words" like *the*, *I*, *of* (called
  **stop words**). Other tests: `<`, `>=`, `<=`, `!=`/`<>`.
- **Any column used anywhere counts toward the bill**, not just the ones in `SELECT`. Sieving on
  `corpus` added its drawer (4.88 MB).
- **`AND` = strict bouncer (both tests), `OR` = relaxed bouncer (either test).**
  `WHERE word_count > 100 AND corpus = 'hamlet'` gave 47 rows. Top word: *the* (995 times).
- **Text matching is case-sensitive:** `HAMLET` (the character's name in speech headings, 407) and
  `hamlet` are different values. `'Hamlet'` would match nothing in `corpus`.
- **Lesson 4: `ORDER BY` lines rows up** (default `ASC` = smallest first, `DESC` = biggest first),
  like children lining up for a photo. Clicking a column header only sorts my screen, not the query.
- **Clause order is fixed:** `SELECT` → `FROM` → `WHERE` → `ORDER BY` → `LIMIT`.
- **Lesson 5: `LIMIT` keeps the first N rows.** `ORDER BY` + `LIMIT` = the "top N" podium pattern.
  `LIMIT` without `ORDER BY` = "some N rows", not "the top N".
- **BigQuery trap:** `LIMIT` doesn't cut the bytes scanned (still 4.88 MB). Only fewer columns does.
- **Comments are sticky notes SQL ignores:** `/* ... */` for many lines, `-- ...` for one line.

- **Git and GitHub basics:** **commit** = sealing a letter in an envelope (a snapshot on my laptop).
  **Push** = taking the envelopes to the post box (sending them to GitHub). You can commit several
  times and push once. On GitHub, the **Commits** page is the project's diary, and clicking a commit
  shows the **diff** (green `+` = added, red `-` = removed, like track changes in Word).
  `git log --oneline` shows the same diary in the terminal.
- **Line endings:** Windows ends lines with CRLF, Mac/Linux with LF, like driving on different
  sides of the road. The warning was harmless. Best practice is a `.gitattributes` file that stores
  everything as LF, so the repo is consistent on any computer.

**Quiz: 4/5**
- ⚠️ Weak spot: **reading error clues.** I missed that `SELECT word, corpus, FROM` breaks because of
  the **extra comma after the last column**. A comma means "another column is coming", so SQL
  tries to read `FROM` as a column name. Look for small punctuation slips first.

**Quiz (Lessons 3–5): 5/5** 🎉
- Fine print: **keywords** aren't case-sensitive (`select` = `SELECT`), but **text values** are
  (`'hamlet'` ≠ `'Hamlet'`).
- Watch for **ties**: many words share the lowest count, so "the 5 least-used" with `LIMIT 5`
  picks 5 of the tied rows, and which ones it picks can change.

---

## Session 3 — 1 November 2026: Lesson 6, counting and adding up (aggregates)

**What we did**
- Lesson 6 in BigQuery on the Shakespeare table: `COUNT(*)`, `AS`, `COUNT(DISTINCT)`,
  `SELECT DISTINCT`, `SUM`, `AVG`, `ROUND`, `MIN`, `MAX`.
- Final query: total 32,446 words in Hamlet, average 6.1 uses per word, min 1, max 995.
- Played data detective: `COUNT(DISTINCT corpus)` said 42 "plays", but Shakespeare wrote ~37.
  Listing the values showed 5 poems: `loverscomplaint`, `rapeoflucrece`, `sonnets`,
  `venusandadonis` and a catch-all `various`. 42 − 5 = 37. ✔️

**What I learned**
- **Aggregates squash many rows into one answer.** Like a teacher saying "there are 28 children"
  instead of calling every name. The result is **one row**.
- **`COUNT(*)` processed 0 B** in BigQuery: the row count is printed on the outside of the box
  (**metadata**, "data about the data"). Adding `WHERE` opens a drawer, so it costs bytes again.
- **`AS` gives a column a name (an alias).** Without it, BigQuery calls it `f0_`, PostgreSQL calls it
  `count`. The exam asks for exact column names, so always alias. Best practice: `snake_case`.
- **`COUNT(*)` vs `COUNT(DISTINCT x)`:** a jar of 100 sweets in 5 colours → 100 vs 5.
  "How many customers?" needs `DISTINCT`; plain `COUNT(*)` counts orders.
- **`SELECT DISTINCT` shows which values; `COUNT(DISTINCT)` says how many.** If the count looks odd,
  list the values. Never trust a column name, and always look inside "various/other/misc".
- **Text sorts character by character, digits before letters**, so `1kinghenryiv` comes first,
  and `'10'` sorts before `'9'` when numbers are stored as text.
- **`COUNT` vs `SUM`** = number of coins vs amount of money in the piggy bank. Hamlet: 5,318 different
  words (`COUNT`), 32,446 words in total (`SUM`).
- **`AVG` = `SUM` ÷ `COUNT`.** I predicted 6.1 before running it. ✔️
- **`ROUND(AVG(x), 2)` is a box inside a box:** the inner function runs first. BigQuery shows `6.1`,
  PostgreSQL shows `6.10`. Same value. ⚠️ In PostgreSQL, `round(x, 2)` needs a `numeric` value.
- **`MIN` / `MAX`** = shortest and tallest kid, no lining up needed.
- **Skew preview:** average 6.1 but max 995. A few giant words pull the average up, like one very tall kid.
- Several aggregates fit in one query, one column per line. Fewer trips to the shop.

**Quiz (Lesson 6): 4.5/5**
- ⚠️ Weak spot: **answer every part of the question.** Q2 asked for the value *and* the number of rows.
  I gave 995 but not "1 row". The all-or-nothing practical punishes skipped parts.

---

## Coming up next
0. **Lesson 7: `GROUP BY`**: one answer *per play* instead of one answer for everything. Then
   `HAVING` and joins, one at a time.
1. HackerRank **SQL (Basic)**: a free, quick first certificate, once the basics above are done.
2. Start DataCamp Premium and the **SQL Fundamentals** track (26 hours). Pick a target month
   for the exam, remembering there are only 30 days from registering to finish both parts.
3. Try DataCamp's readiness quiz and sample practical early, as a baseline.
4. Alongside: window functions in BigQuery (see the Advanced SQL table in `1-sql/EXAM_GUIDE.md`).
5. Later: dbt (`2-dbt/`), then Snowflake (`3-snowflake/`).
