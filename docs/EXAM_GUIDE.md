# Exam Guide: dbt Analytics Engineering Certification

Source: the official exam page,
https://www.getdbt.com/certifications/analytics-engineer-certification-exam
(read on 2026-11-01). Topic wording below is copied exactly from that page.

## The facts

- **Exam version:** dbt **1.11** ("Supported version - 1.11"). My laptop has dbt Core 1.12,
  which includes everything in 1.11.
- **Recommended before sitting it:** "SQL proficiency and at least six months of experience
  working with dbt or dbt Core."
- **Register at:** https://pages.talview.com/dbtlabs/certifications/
- **Number of questions, time limit, passing score, price:** the page has headings for these,
  but the values didn't load in text form. ⚠️ Open the page in a browser and fill these in:
  - Questions: ___
  - Duration: ___
  - Passing score: ___
  - Price: ___
- **The page also has 10 sample questions and a downloadable study guide (version 1.11).**
  Do the sample questions once early on, as a "where am I starting from?" check, and again near the end.

## How to use this checklist

Each topic has three boxes: **Read** (I've read the dbt docs for it), **Built** (I've done
it myself in this repo), **Explain** (I can explain it to a 10-year-old without notes).
Explaining it is the real test. If you can't explain it simply, you don't know it yet.

---

## 1. Developing and optimizing dbt models

| Competency | Read | Built | Explain |
|---|---|---|---|
| Identifying and verifying any raw object dependencies | [ ] | [ ] | [ ] |
| Understanding core dbt materializations | [ ] | [ ] | [ ] |
| Conceptualizing modularity and how to incorporate DRY principles | [ ] | [ ] | [ ] |
| Using commands such as `build`, `run`, `test`, `docs`, `show`, `snapshot`, and `seed` | [ ] | [ ] | [ ] |
| Creating a logical flow of models and building clean DAGs | [ ] | [ ] | [ ] |
| Defining configurations in `dbt_project.yml` | [ ] | [ ] | [ ] |
| Using dbt Packages | [ ] | [ ] | [ ] |
| Creating Python Models | [ ] | [ ] | [ ] |
| Providing access to users to models with the "grants" config | [ ] | [ ] | [ ] |
| Creating snapshots in YAML | [ ] | [ ] | [ ] |
| Selecting the optimal incremental strategy based on a dataset's characteristics | [ ] | [ ] | [ ] |
| Validating model logic and schema definitions in dry-runs using the `--empty` flag | [ ] | [ ] | [ ] |
| Running models in sample mode using the `--sample` flag | [ ] | [ ] | [ ] |
| Understanding advanced dbt materializations such as microbatch | [ ] | [ ] | [ ] |

## 2. Managing dbt models governance

| Competency | Read | Built | Explain |
|---|---|---|---|
| Adding contracts to models to ensure the shape of models | [ ] | [ ] | [ ] |
| Creating different versions of our models and deprecating the old ones | [ ] | [ ] | [ ] |
| Defining constraints in YAML to enforce data integrity at the platform level | [ ] | [ ] | [ ] |

## 3. Debugging data modeling errors

| Competency | Read | Built | Explain |
|---|---|---|---|
| Understanding logged error messages | [ ] | [ ] | [ ] |
| Troubleshooting using compiled code | [ ] | [ ] | [ ] |
| Troubleshooting .yml compilation errors | [ ] | [ ] | [ ] |
| Developing and implementing a fix and testing it prior to merging | [ ] | [ ] | [ ] |
| Managing dbt behavior with flags | [ ] | [ ] | [ ] |

## 4. Troubleshooting and optimizing dbt pipelines

| Competency | Read | Built | Explain |
|---|---|---|---|
| Troubleshooting and managing failure points in the DAG | [ ] | [ ] | [ ] |
| Using dbt clone | [ ] | [ ] | [ ] |

## 5. Implementing dbt tests

| Competency | Read | Built | Explain |
|---|---|---|---|
| Using generic, singular, custom, and custom generic tests on a wide variety of models and sources | [ ] | [ ] | [ ] |
| Testing assumptions for dbt models and sources | [ ] | [ ] | [ ] |
| Implementing various testing steps in the workflow | [ ] | [ ] | [ ] |

## 6. Implementing and Maintaining External Dependencies

| Competency | Read | Built | Explain |
|---|---|---|---|
| Implementing dbt exposures | [ ] | [ ] | [ ] |
| Implementing source freshness | [ ] | [ ] | [ ] |

## 7. Leveraging the dbt state

| Competency | Read | Built | Explain |
|---|---|---|---|
| Understanding state and state selection | [ ] | [ ] | [ ] |
| Using dbt retry | [ ] | [ ] | [ ] |

---

## Already partly covered in harbour-analytics

A head start from the sister project. These still need re-doing here to tick **Built**:
sources (`_xero__sources.yml`), the staging CTE pattern, view materialization, `dbt build`,
`dbt compile` / compiled code, and generic tests (`unique`, `not_null`, `accepted_values`).
