# Analytics Certifications

My study plan and hands-on practice on the way from data analyst to analytics engineer.

## Roadmap

```
Track 1: SQL                   Track 2: dbt                     Track 3: Snowflake
HackerRank SQL (free)     ──►  dbt Analytics Engineering   ──►  Snowflake trial project
DataCamp SQL Associate         Certification (v1.11)            SnowPro Core
Advanced SQL in BigQuery
```

| Track | Folder | Status |
|---|---|---|
| 1. SQL | [`1-sql/`](1-sql/EXAM_GUIDE.md) | In progress |
| 2. dbt | [`2-dbt/`](2-dbt/EXAM_GUIDE.md) | Next: exam guide ready |
| 3. Snowflake | [`3-snowflake/`](3-snowflake/README.md) | Later |

Why this order: SQL is the base for everything else. dbt is the core analytics engineering
tool and works on any warehouse. Snowflake is the warehouse most often named in Auckland
analytics engineering job ads.

Each exam guide is a checklist of the official competencies: **Read → Built → Explain**.
A competency only counts once I can explain it simply. Progress is logged in
[`docs/STUDY_LOG.md`](docs/STUDY_LOG.md).

Portfolio project: [harbour-analytics](https://github.com/yabgestopa/harbour-analytics), a
Xero → Fivetran → BigQuery → dbt → Power BI pipeline.
