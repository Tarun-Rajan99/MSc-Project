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
- The `drop_dest_comps.ipynb` `drop_failrate`,`drop_nauth`,`drop_src_comps`,`drop_time`, contains the composite stability results of dropping that feature
- `ablation_analysis.ipynb` - combines all the ablation configurations results

- The `ablation_analysis` folder contains the code for the ablation analysis




