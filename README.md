# NHS Hospital Discharge Delay Analysis

**Author:** Noura Lakrimdi

**Status:** In progress — project setup only. Data cleaning, SQL analysis and the dashboard have not yet been completed. No findings are claimed.

## Project question

Which NHS acute trusts have persistent discharge delays, and how have those delays changed over time?

This independent portfolio project will use public, aggregate NHS England data to examine discharge-delay trends. It connects a Medical Physiology background with practical data analysis.

## Data source

[NHS England: Discharge Ready Date](https://www.england.nhs.uk/statistics/statistical-work-areas/discharge-delays/discharge-ready-date/)

Start with one monthly file and the accompanying technical guidance. Expand to 12 consecutive months with comparable definitions after validating the first file. Record the exact source URLs, reporting periods, download dates and revision status in `data/source_manifest.csv`.

## Planned deliverables

- A Python cleaning pipeline with documented quality checks.
- A SQLite database and SQL queries for trust-level trends and comparisons.
- A Power BI dashboard with time and trust filters.
- A short report with three supported findings and explicit limitations.
- Instructions for reproducing the analysis.

## Setup

Clone the repository, then run:

```bash
python -m venv .venv
```

Activate the environment:

- Windows PowerShell: `.venv\Scripts\Activate.ps1`
- macOS/Linux: `source .venv/bin/activate`

Install the starter dependencies:

```bash
python -m pip install -r requirements.txt
```

SQLite is available through Python's standard-library `sqlite3` module. Power BI is a separate dashboard tool.

These commands prepare the environment; there is no analysis pipeline to run yet.

## Work plan

| Stage | Task | Completion criterion |
|---|---|---|
| 1. Understand | Download one monthly file and its guidance | Explain each selected measure, unit, denominator and row type |
| 2. Inspect | Check headings, reporting periods and trust identifiers | Produce a data dictionary and initial quality summary |
| 3. Clean | Standardise comparable monthly files in Python | Preserve suppression flags and document duplicates and missingness |
| 4. Analyse | Load cleaned data into SQLite and write SQL | Reproduce trust trends and comparisons with auditable queries |
| 5. Visualise | Build a Power BI dashboard | Show trends, coverage and clearly labelled comparisons |
| 6. Communicate | Write findings and publish screenshots | Every claim links to a reproducible output |

## Analytical rules

- Use provider codes where available; names can change.
- Separate trust rows from national or regional totals to avoid double counting.
- Preserve suppressed and unavailable values; never replace them with zero.
- Follow the source guidance when choosing denominators and weighting aggregate measures.
- Check reporting coverage and definition changes before comparing months.
- Consider differences in patient populations and discharge pathways when comparing trusts.
- Describe associations; aggregate data alone cannot establish causes of delays.
- Do not infer individual patient outcomes from trust-level statistics.

## Intended project structure

Only the setup files are currently present. Create these directories as you complete each stage:

- `data/raw/`: unchanged public source files, kept locally.
- `data/processed/`: cleaned outputs, kept locally.
- `src/`: reusable Python scripts.
- `sql/`: schema and analytical queries.
- `dashboard/`: dashboard file and screenshots.
- `reports/`: data dictionary, quality checks and findings.

See [data instructions](data/README.md).

## First task

Download one monthly dataset and its guidance. Record:

1. The reporting month and publication/revision status.
2. Which sheet or CSV table contains trust-level observations.
3. The provider identifier and the meaning of each chosen metric.
4. The symbols used for suppressed or missing values.

Do not calculate rankings until these definitions are clear.

## How to cite

If you use this repository, please cite:

```text
Lakrimdi, N. (2026). NHS Hospital Discharge Delay Analysis [Research project repository; work in progress]. GitHub. https://github.com/Noural06/nhs-discharge-delay-analysis
```

Also record the commit SHA or release used and your access date. Cite NHS England separately as the data source.

## Acknowledgement

Source data: NHS England. This is an independent student portfolio project, not an NHS-endorsed publication. Check the source's reuse terms before redistributing data.
