# capstone-recommender-misalignment

# Capstone Step 2 — Data Collection

## Project Goal
Build a machine learning system to detect **preference misalignment** in recommendation settings by comparing explicit user ratings (what users say they like) to proxy engagement signals (what users appear to engage with).

## Datasets Used

### 1. MovieLens 1M (Explicit Ratings Dataset)
- Source: https://grouplens.org/datasets/movielens/1m/
- Contains: user_id, movie_id, rating, timestamp
- Total interactions: ~1,000,000 ratings
- Purpose: Serves as explicit user preference data

Sample file stored in:
`data/raw/movielens_sample.csv`

---

### 2. Amazon Video Games Reviews (Implicit + Text Dataset)
- Source: UCSD Amazon Reviews 2023 dataset
- Subset: Video Games 5-core dataset
- Contains:
  - overall rating
  - reviewerID
  - asin (product ID)
  - reviewText
  - summary
  - unixReviewTime
- Total interactions: ~497,000 reviews
- Purpose: Provides engagement-rich behavioral and textual signals

Sample file stored in:
`data/raw/amazon_videogames_sample.csv`

---

### 3. Derived Proxy Engagement Dataset (Misalignment Detection)

A synthetic engagement proxy was constructed using MovieLens 1M:

Engagement proxy defined as:

engagement_proxy = item_rating_count × user_rating_count

High engagement threshold:
- Top 20% of engagement_proxy values

Misalignment defined as:
- High engagement item
- Explicit rating ≤ 2

Proxy dataset statistics:
- Total rows: 1,000,209
- Misalignment rate: ~2.3%
- Misaligned interactions: 22,963

Sample file stored in:
`data/raw/proxy_engagement_sample.csv`

## Repository Structure
- `notebooks/` — dataset exploration notebooks
- `src/` — scripts for downloading/processing datasets
- `data/`
  - `external/` — raw downloaded datasets stored locally (ignored by git)
  - `raw/` — small sample files (optional)
  - `processed/` — cleaned/derived tables (small samples only)

## How to Reproduce (Step 2)
- Dataset download / preparation scripts will be placed in `src/`
- Exploration notebooks will be placed in `notebooks/`
- Raw datasets are not committed to GitHub. Links and instructions will be documented in `docs/data_sources.md`.

## Next Steps
- Download and explore MovieLens 1M
- Download and explore an Amazon Reviews subset
- Create or select a proxy engagement dataset/table
- Document sources and basic dataset statistics
