# MSc-Project

This repo contains the work for the MSc Statistics research project at Imperial College London.

The code for reproducing the research is contained in `03_code` using the authentication dataset from https://csr.lanl.gov/data/cyber1/. It is structured as follows: 

- **`feature_construction`**:
  - `data_summary_stats.ipynb` — summary statistics of the data.
  - `feature_engineering.ipynb` — feature engineering and EDA plots 

- **`choosing_k`**:
  - `choosing_k.ipynb` - selection of $K$ for $k$-means clustering


- **`jaccard`**:
  - `jaccard.ipynb` - Jaccard index results

- **`ARI`, `VI,` and `PSI`**:
  - `ARI.ipynb`, `VI.ipynb,` and `PSI.ipynb` - ARI, 1 - NVI and PSI clustering stability results
 

- **`composite_stability`**:
  - `composite_stability.ipynb` - baseline composite stability index results


- **`ablation_analysis`**:
  - `drop_dest_comps.ipynb` `drop_failrate.ipynb`, `drop_nauth.ipynb`, `drop_src_comps.ipynb` and`drop_time.ipynb` contain the composite stability results of dropping that feature
  - `ablation_analysis.ipynb` - combines all the ablation configuration results





