# Data instructions

Use only public, aggregate NHS England publications for this project.

Source: https://www.england.nhs.uk/statistics/statistical-work-areas/discharge-delays/discharge-ready-date/

## Start with one file

1. Download one monthly file and the accompanying technical guidance.
2. Create `data/raw/` locally and keep the downloaded file unchanged.
3. Record the source in `data/source_manifest.csv`.
4. Inspect the table before deciding on a cleaned schema.

Suggested manifest columns:

```text
filename,source_url,reporting_month,downloaded_on,revision_status,guidance_url
```

## Cleaning checklist

- Identify trust-level rows and exclude aggregate totals from trust comparisons.
- Document the row grain: one observation for which provider, period and measure?
- Use the technical guidance to define units, denominators and weighting.
- Preserve source flags for suppressed, missing and unavailable values.
- Check duplicates at the documented row grain.
- Record changes in trust codes, coverage and metric definitions.
- Save derived files to `data/processed/`; do not overwrite raw files.

Raw files, processed data and local databases are ignored by git. Commit the manifest, cleaning code, data dictionary and aggregate quality summaries so readers can reproduce the workflow.

No data has been downloaded or analysed as part of this initial setup.
