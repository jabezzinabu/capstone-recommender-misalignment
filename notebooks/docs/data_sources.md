Data Sources
1. MovieLens 1M Dataset

Source:
https://grouplens.org/datasets/movielens/1m/

Description:
The MovieLens 1M dataset contains 1,000,209 explicit user ratings of movies, including user_id, movie_id, rating, and timestamp.

How it was collected:
The dataset was downloaded directly from the official GroupLens website as a compressed archive (.zip). The files were extracted locally and stored in:

data/external/movielens-1m/

Only small sample files are committed to GitHub for reproducibility:

data/raw/movielens_sample.csv
2. Amazon Video Games Reviews Dataset

Source:
UCSD Amazon Reviews 2023 Collection
https://nijianmo.github.io/amazon/index.html

Subset Used:
Video Games 5-core dataset

Description:
This dataset contains approximately 497,000 product reviews including:

overall rating

reviewerID

asin (product ID)

reviewText

summary

unixReviewTime

How it was collected:
The dataset was downloaded as a JSON file from the official UCSD Amazon dataset page. It was converted to CSV format locally and stored in:

data/external/amazon/

A small sample file is committed to GitHub:

data/raw/amazon_videogames_sample.csv
3. Derived Proxy Engagement Dataset

A synthetic engagement proxy dataset was constructed from the MovieLens 1M dataset.

Construction Method:

item_rating_count = total ratings per movie

user_rating_count = total ratings per user

engagement_proxy = item_rating_count × user_rating_count

High engagement was defined as the top 20% of engagement_proxy values.

Misalignment was defined as:

High engagement interaction

Explicit rating ≤ 2

The full derived dataset contains:

1,000,209 rows

Approximately 2.3% misalignment rate

The full dataset is stored locally in:

data/external/

A sample file is committed:

data/raw/proxy_engagement_sample.csv
Storage Policy

Large raw datasets are not committed to GitHub.
They are stored locally in data/external/ and excluded via .gitignore.

Only small sample files are included in the repository for demonstration and reproducibility.
