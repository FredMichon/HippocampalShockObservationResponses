# The Intermediate Hippocampus Integrates Shock-Observation and Spatial Information during Observational Fear Memory

**Frédéric Michon Linde, Valeria Gazzola & Christian Keysers**  
Netherlands Institute for Neuroscience · University of Amsterdam  

---

## Overview

This repository contains the analysis notebooks and summary data tables used to generate statistical results and figures in the manuscript. Male rats were recorded with Neuropixels probes spanning the dorsal, intermediate, and ventral hippocampus while they observed a conspecific receive footshocks in one context (shock context) but not in another (safe context). Neural activity was tracked across three phases: shock observation, post-learning rest, and contextual recall.

The main findings are:
- Pyramidal neurons were recruited by shock observation, with an enrichment of shock-excited cells in the **intermediate hippocampus**.
- Shock-observation responses scaled with place-field firing, revealing a **conjunctive spatial–social code** in the dorsal and intermediate hippocampus.
- Shock-context spatial representations were comparatively **stabilised** in the intermediate hippocampus after learning.
- Post-learning SWRs preferentially **reactivated shock-context ensemble patterns**, most strongly in animals expressing contextual freezing at recall (RECALLER).

---

## Repository contents

| Notebook | Figures |
|---|---|
| `Analysis_behavior.ipynb` | Fig. 1b–c · Ext. Data Fig. 1a–g |
| `Analysis_ShockObs_response.ipynb` | Fig. 2c–d · Fig. 3c · Ext. Data Fig. 3a–b |
| `Analysis_spatial_representation.ipynb` | Fig. 4b–c · Ext. Data Fig. 4a–b |
| `Analysis_SWR_reactivation.ipynb` | Fig. 5b–e · Ext. Data Fig. 5d–f |

Each notebook loads one or more summary Parquet/CSV tables (see **Data** below), reproduces the statistical tests reported in the manuscript, and generates the corresponding figure panels.

---

## Data

Summary data tables are deposited at [(https://osf.io/7jkn9/overview)]. Set the `Folder_path` variable at the top of each notebook to the directory containing these files:

| File | Used in |
|---|---|
| `table_behavior_freezing.csv` | `Analysis_behavior` |
| `table_behavior_vicinity.csv` | `Analysis_behavior` |
| `table_behavior_shockobs.parquet` | `Analysis_behavior` |
| `table_unit_ShockObs.parquet` | `Analysis_ShockObs_response` |
| `table_place_shock_coding.parquet` | `Analysis_ShockObs_response` |
| `table_place_shock_SVM.parquet` | `Analysis_ShockObs_response` |
| `table_spatial_firing.parquet` | `Analysis_spatial_representation` |
| `table_spatial_similarities.parquet` | `Analysis_spatial_representation` |
| `table_spatial_PrePostsimilarities.parquet` | `Analysis_spatial_representation` |
| `table_spatial__context_similarities.parquet` | `Analysis_spatial_representation` |
| `table_EV.parquet` | `Analysis_SWR_reactivation` |
| `table_EV_SWRarea.parquet` | `Analysis_SWR_reactivation` |
| `table_EV_cellarea.parquet` | `Analysis_SWR_reactivation` |
| `table_SWR.parquet` | `Analysis_SWR_reactivation` |
| `table_SWRu.parquet` | `Analysis_SWR_reactivation` |
| `table_SWRu_corr.parquet` | `Analysis_SWR_reactivation` |

---

## Dependencies

The notebooks were developed with Python 3.8 and require:

```
numpy · pandas · scipy · statsmodels · pingouin · seaborn · matplotlib
```
---

## Contact

Frédéric Michon Linde — michon.f.p@gmail.com  
Christian Keysers — c.keysers@nin.knaw.nl
