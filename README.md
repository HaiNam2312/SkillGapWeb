# Melbourne Graduate Skills Map

What do graduate and junior roles in Melbourne actually ask for? A small, hand-labelled dataset of job ads (data analyst, data scientist, software developer, business analyst, economist) plus a web tool that shows which skills to prioritise for a chosen role.

> Status: work in progress. Dataset collection started [5/11/2026].

## Question
For someone about to graduate (or recently graduated) in Melbourne: if I am aiming for role X, which skills should I learn and show first?

## What is in this repo
- `data/ads.csv` - one row per job ad, labelled by hand (no raw ad text)
- `skills_taxonomy.yaml` - skill list with aliases (versioned, see CHANGELOG)
- `schema.md` - field definitions and labelling rules
- (planned) `analysis/` - Python notebooks, `web/` - the Skill Gap Checker

## Method (short)
Ads were collected manually between [5/11/2026 - ..] from [LinkedIn, Indeed, Seek]. Skills were labelled by hand using the rules in `schema.md`; an automatic extractor is compared against the hand labels.

## Limitations
- Small sample (N = [..]) collected by one person, so it reflects the ads I could find, not the whole market.
- Collected during [month/year]; hiring varies by season.
- Skills are labelled only when explicitly mentioned.

## Not legal or career advice
Findings describe the collected ads only.