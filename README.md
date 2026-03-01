# capstone-recommender-misalignment

# Capstone Step 2 - Data Collection

## Project Goal

Build a machine learning system to detect **preference misalignment** in recommendation settings by comparing explicit user ratings (what users say they like) to proxy engagement signals (what users appear to engage with).

---

## Datasets Used

### 1. MovieLens 1M (Explicit Ratings Dataset)

**Source:**
[https://grouplens.org/datasets/movielens/1m/](https://grouplens.org/datasets/movielens/1m/)

**Description:**
The MovieLens 1M dataset contains 1,000,209 explicit user ratings of movies, including user_id, movie_id, rating, and timestamp.

**Purpose:**
Serves as structured explicit feedback data for modeling user satisfaction.

**Total interactions:** ~1,000,000 ratings

Sample file stored in:
`data/raw/movielens_sample.csv`

---

### 2. Amazon Video Games Reviews (Implicit + Text Dataset)

**Source:**
UCSD Amazon Reviews 2023 Collection
[https://nijianmo.github.io/amazon/index.html](https://nijianmo.github.io/amazon/index.html)

**Subset Used:**
Video Games 5-core dataset

**Description:**
This dataset contains approximately 497,000 product reviews including:

* overall rating
* reviewerID
* asin (product ID)
* reviewText
* summary
* unixReviewTime

**Purpose:**
Provides real-world engagement and behavioral signals that complement structured rating data.

**Total interactions:** ~497,000 reviews

Sample file stored in:
`data/raw/amazon_videogames_sample.csv`

---

### 3. Derived Proxy Engagement Dataset (Misalignment Detection)

A synthetic engagement proxy dataset was constructed from the MovieLens 1M dataset.

**Construction:**

* `item_rating_count` = total ratings per movie
* `user_rating_count` = total ratings per user
* `engagement_proxy = item_rating_count × user_rating_count`

High engagement defined as top 20% of engagement_proxy values.

Misalignment defined as:

* High engagement interaction
* Explicit rating ≤ 2

**Proxy dataset statistics:**

* Total rows: 1,000,209
* Misalignment rate: ~2.3%
* Misaligned interactions: 22,963

Sample file stored in:
`data/raw/proxy_engagement_sample.csv`

---

## Repository Structure

* `notebooks/` — dataset exploration notebooks
* `src/` — scripts for downloading/processing datasets
* `data/`

  * `external/` — raw downloaded datasets stored locally (ignored by git)
  * `raw/` — small sample files committed for reproducibility
  * `processed/` — cleaned or derived tables (small samples only)
* `docs/` — documentation including data source descriptions

---

## Data Storage Policy

Large raw datasets are **not committed to GitHub**.
They are stored locally in `data/external/` and excluded via `.gitignore`.

Only small sample files are included in the repository for demonstration and reproducibility.

Full data source documentation is available in:
`docs/data_sources.md`

