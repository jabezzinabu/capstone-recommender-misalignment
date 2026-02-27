# capstone-recommender-misalignment

# Capstone Step 2 — Data Collection

## Project Goal
Build a machine learning system to detect **preference misalignment** in recommendation settings by comparing explicit user ratings (what users say they like) to proxy engagement signals (what users appear to engage with).

## Datasets (Explored)
1) **MovieLens 1M** — user/movie ratings with timestamps  
2) **Amazon Reviews** — product ratings (and optional review text/metadata)  
3) **Proxy Engagement Dataset** — a dataset representing engagement signals (either an existing dataset if feasible, or a derived proxy table created from MovieLens/Amazon data)

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
