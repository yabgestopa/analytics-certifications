# Track 1: SQL Certifications

Goal: SQL proof on my CV for analyst roles, and solid SQL before dbt.

| Certificate | Cost | Why |
|---|---|---|
| **DataCamp SQL Associate** (main) | Included in DataCamp Premium (~US$14–25/month) | Practical, business-problem exam; prep courses included |
| **HackerRank SQL: Basic, Intermediate, Advanced** | Free | Quick CV wins; Advanced stretches past DataCamp's level |
| **Window functions + advanced SQL** (no certificate) | Free, in BigQuery | The skills interviews test most; feeds straight into dbt |

---

## DataCamp SQL Associate

Sources (read 2026-11-01):
- https://www.datacamp.com/certification/sql-associate
- https://support.datacamp.com/hc/en-us/articles/19267574171927-SQL-Associate (full requirements)

### The facts

- **Two parts, both within 30 days of registering:**
  1. **SQ101, timed exam.** The support article says 60 minutes (most finish in ~45). The
     certification page says up to 2 hours. Plan for 60.
  2. **SQ501P, practical exam.** 4 hours, **2 attempts**, graded automatically.
     ⚠️ **You must get every part of the practical right to pass.** Partial credit doesn't count.
- **SQL dialect: PostgreSQL.** Not BigQuery. Practise these topics in PostgreSQL (see "Dialect
  traps" below).
- **Cost:** included with a DataCamp Premium subscription, with no extra exam fee. Prep
  courses and practice exams are included.
- **Expiry:** DataCamp's general FAQ says technology certifications last **2 years**, then you're
  invited to retake. Not confirmed for SQL Associate specifically.
- **Prep track named on the page:** "SQL Fundamentals" (26 hours).
  https://www.datacamp.com/tracks/sql-fundamentals
- **Before booking:** do the **readiness quiz** and the **sample practical exam**:
  https://app.datacamp.com/certification/technology-certifications/sql/associate/practical-hub
- Proctoring and the SQ101 retake limit aren't stated on the pages.

### How to use this checklist

**Read** = I've studied it. **Built** = I've written the query myself on real data and it
worked. **Explain** = I can explain it to a 10-year-old without notes.

### SQ101: timed exam

Wording copied from the support article.

| Competency | Read | Built | Explain |
|---|---|---|---|
| Interpret a database schema and explain database design concepts (such as normalization, design, schemas, data storage options) | [ ] | [ ] | [ ] |
| Perform data extraction, joining, and aggregation tasks | [ ] | [ ] | [ ] |
| Perform cleaning tasks to prepare data for analysis | [ ] | [ ] | [ ] |
| Assess data quality and perform validation tasks | [ ] | [ ] | [ ] |
| Calculate metrics to effectively report characteristics of data and relationships between features using PostgreSQL | [ ] | [ ] | [ ] |

### SQ501P: practical exam

**1. Perform data extraction, joining, and aggregation tasks**

| Competency | Read | Built | Explain |
|---|---|---|---|
| Aggregate numeric and categorical variables and dates by groups using PostgreSQL | [x] | [ ] | [ ] |
| Interpret a database schema and combine multiple tables by rows or columns using PostgreSQL | [ ] | [ ] | [ ] |
| Extract data based on different conditions using PostgreSQL | [x] | [x] | [ ] |
| Use subqueries to reference a second table (e.g. a different table, an aggregated table) within a query in PostgreSQL | [ ] | [ ] | [ ] |

**2. Perform cleaning tasks to prepare data for analysis**

| Competency | Read | Built | Explain |
|---|---|---|---|
| Match strings in a dataset with specific patterns | [ ] | [ ] | [ ] |
| Convert values between data types | [ ] | [ ] | [ ] |
| Clean categorical and text data by manipulating strings | [ ] | [ ] | [ ] |
| Clean date and time data | [ ] | [ ] | [ ] |

**3. Assess data quality and perform validation tasks**

| Competency | Read | Built | Explain |
|---|---|---|---|
| Identify and replace missing values | [ ] | [ ] | [ ] |
| Perform different types of data validation tasks (e.g. consistency, constraints, range validation, uniqueness) | [ ] | [ ] | [ ] |
| Identify and validate data types in a data set | [ ] | [ ] | [ ] |

**4. Interpret a database schema and explain database design concepts**

| Competency | Read | Built | Explain |
|---|---|---|---|
| Explain the design schema of a database | [ ] | [ ] | [ ] |
| Identify from a schema how tables are connected and how to join multiple tables | [ ] | [ ] | [ ] |
| Explain concepts in database design (normalization, design schemas, data storage options, etc) | [ ] | [ ] | [ ] |

**5. Calculate metrics to report characteristics of data and relationships between features**

| Competency | Read | Built | Explain |
|---|---|---|---|
| Calculate measures of center (e.g. mean, median, mode) for variables using PostgreSQL | [x] | [ ] | [ ] |
| Calculate measures of spread (e.g. range, standard deviation, variance) for variables using PostgreSQL | [ ] | [ ] | [ ] |
| Calculate skewness for variables using PostgreSQL | [ ] | [ ] | [ ] |
| Calculate missingness for variables and explain its influence on reporting characteristics of data and relationships in PostgreSQL | [ ] | [ ] | [ ] |

### Dialect traps: PostgreSQL vs BigQuery

Same ideas, different spelling. Check each one against the PostgreSQL docs when you reach it.

| Task | PostgreSQL (exam) | BigQuery (Harbour) |
|---|---|---|
| Median | `percentile_cont(0.5) within group (order by x)` | `percentile_cont(x, 0.5) over ()` |
| Mode | `mode() within group (order by x)` | no built-in; count and pick the top value |
| Convert type | `x::integer` or `cast(x as integer)` | `cast(x as int64)` / `safe_cast(...)` |
| Pattern match | `like`, `ilike` (case-insensitive), `~` (regex) | `like`, `regexp_contains(...)` |
| Skewness | no built-in; build it from `avg` and `stddev` | same, no built-in |
| Round to 2 places | `round(x, 2)` needs `x` to be `numeric`; cast doubles first (`round(x::numeric, 2)`) | `round(x, 2)` works on any number |
| Name of an unnamed column | `count`, `avg`, ... (the function name) | `f0_`, `f1_`, ... (always alias with `as`) |

---

## HackerRank SQL certificates (free)

https://www.hackerrank.com/skills-verification. Search "SQL". Each is a short timed online test.

| Certificate | Done | Date | Notes |
|---|---|---|---|
| SQL (Basic) | [ ] | | |
| SQL (Intermediate) | [ ] | | |
| SQL (Advanced) | [ ] | | |

---

## Advanced SQL (no certificate; this is what interviews test)

Practise in BigQuery (free) on the Harbour Xero data or BigQuery public datasets.

| Skill | Read | Built | Explain |
|---|---|---|---|
| Window functions: `row_number`, `rank`, `dense_rank` | [ ] | [ ] | [ ] |
| Window functions: running totals, moving averages (`sum() over (order by ...)`) | [ ] | [ ] | [ ] |
| `lag` / `lead`: compare with the previous or next row | [ ] | [ ] | [ ] |
| `partition by`: a separate window per group | [ ] | [ ] | [ ] |
| CTEs: breaking a hard question into steps | [ ] | [ ] | [ ] |
| Join fan-out: spotting when a join duplicates rows | [ ] | [ ] | [ ] |
| Conditional aggregation: `sum(case when ... then ... end)` | [ ] | [ ] | [ ] |
| NULL handling: `coalesce`, NULLs in joins, filters and `count` | [ ] | [ ] | [ ] |
| Dates: truncating, differences, generating date ranges | [ ] | [ ] | [ ] |
| Reading a query plan / cutting the bytes scanned | [ ] | [ ] | [ ] |
