# Dataset schema (one row = one job ad)

Keep the raw ad text OUT of the public repo (copyright). Publish only the labelled fields below.

| Field | Type | Notes |
|---|---|---|
| ad_id | string | your own id, e.g. A001 |
| date_collected | date | when you saw the ad |
| date_posted | date, optional | if shown |
| source_type | enum | job board / company careers page / university board / other (do not scrape automatically) |
| role_group | enum | data_analyst, data_scientist, software_developer, business_analyst, economist |
| title_raw | string | the original job title |
| seniority_label | enum | graduate / junior / entry-level / other |
| years_experience_min | int or null | null if not stated |
| degree_required | enum | none / bachelor / master / unspecified |
| work_rights | enum | citizen_or_pr_only / any_valid_work_rights / not_stated |
| company_type | enum | big4_consulting / bank_finance / government / startup / corporate / university_research / other |
| industry | string | free text, normalise later |
| work_mode | enum | onsite / hybrid / remote / not_stated |
| location | string | e.g. Melbourne CBD |
| salary_min, salary_max | int, optional | AUD per year, only if stated |
| skills_required | list of skill ids | from skills_taxonomy.yaml |
| skills_preferred | list of skill ids | |
| labelled_by | enum | manual / auto |
| notes | string | anything odd |

## Labelling rules (write these down BEFORE you start, then stick to them)

1. required = wording like "must", "essential", "required", "you will have"; preferred = "desirable", "nice to have", "bonus", "advantageous". If unclear, put it in required and flag it in notes.
2. Label only skills explicitly mentioned. Do not infer (e.g. do not add SQL because the ad says "databases").
3. Ambiguous aliases (r, go, c, sas, excel used as a verb) count only with clear context, e.g. "R, Python" or "R programming".
4. If a skill is missing from the taxonomy, add it to the notes first; add it to the taxonomy in batches and log in CHANGELOG.md.
5. Re-label 20 random ads a few days later without looking at your first labels, then measure agreement (this is your intra-rater check, and the baseline for the auto-extractor).

## Why work_rights is worth keeping
Many graduate roles restrict applicants to citizens or permanent residents. For graduates on other visas, that is often the first thing they need to know, and it is rarely shown in job-ad statistics.