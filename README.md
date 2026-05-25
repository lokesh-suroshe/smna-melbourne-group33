
# Listening to the City — r/melbourne (COSC 2671 Assignment 2)

## What this is

Python notebook pipeline for **RQ1** (LDA topics), **RQ2** (VADER sentiment + suburb mentions), and **RQ3** (directed reply network, centrality, Louvain communities, community–topic alignment).

## How to run

1. Install dependencies (Section 1 of the notebook), or:

   ```bash
   pip install convokit pandas numpy scikit-learn networkx matplotlib seaborn vaderSentiment python-louvain tqdm
   ```

2. Open `melbourne_analysis.ipynb` and **Run All** (first run downloads ConvoKit data; may take several minutes).

3. Outputs:
   - `figures/fig1–fig7.png` — report figures (incl. degree distribution)
   - `results/summary.json` — key counts for the report
   - `results/sample_data.csv`, `results/sample_edges.csv` — submission sample (<10 MB)
   - `results/centrality.csv` — per-user centrality and clustering

## Data

- **Source:** ConvoKit corpus `subreddit-melbourne` (public Reddit archive).
- **No API keys** required.
- Corpus is cached locally after the first download.

## Notes for markers

- `MAX_UTTS = 60000` subsamples **whole conversations** (reproducible) so reply edges stay valid; see report limitations.
- HD metrics in `summary.json`: reciprocity, mean clustering, degree assortativity, LDA perplexity.
- Reply network uses users with total degree ≥ 2 (`MIN_DEGREE`).
- Suburb list excludes the token `city` (too ambiguous); `cbd` is kept.

## Submission bundle

- `melbourne_analysis.ipynb`
- `figures/`
- `results/` (sample + summary)
- Report PDF and Worksheet are submitted separately on Canvas.
=======
# smna-melbourne-group33
