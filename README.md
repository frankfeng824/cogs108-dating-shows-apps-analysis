# Dating Show Popularity vs. Dating App Activity

A team data-analysis project from UCSD COGS 108 investigating the relationship between U.S. reality dating show popularity and dating app activity from 2019 to 2026.

**Team:** Anisha Ramesh, Alisa Liao, Junyou Feng, Derek Xu
**Course:** COGS 108 — Data Science in Practice, UC San Diego

## Research question

How is U.S. reality dating show popularity — measured by average per-episode ratings and per-season viewership — associated with changes in U.S. dating app activity (Tinder, Bumble, Hinge), measured by annual revenue and annual user counts, from 2019–2026?

**Hypothesis:** higher viewership/ratings in a season would be associated with higher app user counts and revenue in the same or following year — though not expected to hold every year given confounders (economic conditions, app-side changes).

## Data

- **Show ratings:** IMDb ratings for every episode of Love Island USA, The Bachelor, and Love Is Blind (436 episodes; mean rating 6.89). Limitation: raters are self-selected, engaged viewers.
- **Show viewership:** per-episode viewership for The Bachelor seasons 23–29 (TVSeriesFinale); Netflix Engagement Report (Jan–Jun 2023, 18,214 rows) watch hours for Love Is Blind S1–4 and Love Island USA S1–4, normalized as viewers = watch hours ÷ season runtime.
- **Dating app activity:** annual revenue and user counts for Bumble, Hinge, and Tinder, 2019–2025 (businessofapps.com); Tinder user counts unavailable.
- Final analysis sample: 15 show-season observations.

## Methods

Data cleaning and exploration with pandas; visualizations with Seaborn and Matplotlib (distributions, trends, boxplots, scatter plots with OLS fit and 95% CI); 12 OLS regression models (6 predictors × 2 outcomes: total app revenue, total app users), with log transforms for skewed viewership and Newey-West robust standard errors.

## Key findings

- Ratings rose over time for The Bachelor and Love Island USA; Love Is Blind stayed lower but stable; Love Is Blind viewership surged in 2023 while The Bachelor slowly lost viewers.
- Surprise: within each show, higher-rated seasons tended to have *fewer* viewers — likely rater self-selection bias. No Pearson correlation was significant at α = 0.05.
- Regression: generally positive associations, strongest for The Bachelor (log viewership → revenue adj. R² 0.906 — suspiciously high, likely an artifact of the tiny yearly sample); results differ depending on whether revenue or user counts is the outcome.
- Stated clearly in the analysis: correlation ≠ causation; tiny sample, public-data availability, and missing Tinder user data are key limitations.

## My contributions (Junyou Feng)

- Helped frame the research hypothesis and interpret relationships across the episode-rating, viewership, and app-activity datasets.
- Contributed background research, methodology, and analysis (author roles as recorded in the project notebooks).
- Produced the team's Data & EDA video presenting data sources, visual trends, and limitations.

*Team project — full notebooks live in the course's private project repository; this repo documents the project narrative.*
