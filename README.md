# The Intermediate Hippocampus Integrates Shock-Observation and Spatial Information during Observational Fear Memory

**Frédéric Michon Linde, Valeria Gazzola & Christian Keysers**  
Netherlands Institute for Neuroscience · University of Amsterdam  

---

## Overview

This repository contains the analysis notebooks and summary data tables used to generate statistical results and figures in the manuscript. Male rats were recorded with Neuropixels probes spanning the dorsal, intermediate, and ventral hippocampus while they observed a conspecific receive footshocks in one context (shock context) but not in another (safe context). Neural activity was tracked across three phases: shock observation, post-learning rest, and contextual recall.

The main findings are:
- Pyramidal neurons were recruited by shock observation, with an enrichment of shock-excited cells in the **intermediate hippocampus**.
- Shock-observation responses scaled with place-field firing, revealing a **conjunctive spatial-other's distress code** in the dorsal and intermediate hippocampus.
- Shock-context spatial representations were comparatively **stabilised** in the intermediate hippocampus after learning.
- Post-learning SWRs preferentially **reactivated shock-context ensemble patterns**, most strongly in animals expressing contextual freezing at recall (RECALLER).

Animals are classified throughout as **RECALLER** or **NON-RECALLER** based on whether they show differential (shock > safe context) freezing at recall.

---

## Repository contents

Each figure/extended-data figure has its own notebook. Notebooks load one or more panel-specific Parquet tables (see **Data** below), reproduce the statistical tests reported in the manuscript, and generate the corresponding figure panel(s).

| Notebook | Figure panels reproduced | Data file(s) required |
|---|---|---|
| `Figure1.ipynb` | Fig. 1b (immobility change, shock vs. safe context), Fig. 1c (RECALLER/NON-RECALLER split) | `Fig1bc.parquet` |
| `Figure2.ipynb` | Fig. 2b (example unit waveforms & shock PSTHs), Fig. 2c (population shock-response heatmap by subregion), Fig. 2d (AUC shock-decoding by subregion & recall status) | `Fig2b.parquet`, `Fig2c.parquet`, `Fig2d.parquet` |
| `Figure3.ipynb` | Fig. 3c (spatial firing rate vs. shock-evoked Δrate, conjunctive spatialsocial code) | `Fig3c.parquet` |
| `Figure4.ipynb` | Fig. 4b (baseline→recall representational distance by context), Fig. 4c (safeshock distance by phase & recall status) | `Fig4b.parquet`, `Fig4c.parquet` |
| `Figure5.ipynb` | Fig. 5b (SWR explained variance, EV/REV by phase), Fig. 5c (EV by SWR-originating subregion), Fig. 5de (EV by cell-pair subregion & Δ(shock−safe) by recall status) | `Fig5b.parquet`, `Fig5c.parquet`, `Fig5d.parquet` |
| `SupplementaryFigure1.ipynb` | Ext. Data Fig. 1ag (behavioral tracking: immobility, occupancy/proximity to divider, demonstrator vicinity, pupil diameter, eye movement, speed, distance) | `SuppFig1a.parquet` … `SuppFig1g.parquet` |
| `SupplementaryFigure2.ipynb` | Ext. Data Fig. 2bc (probe-track unit density along the dorsoventral axis; ShockObs⁺ unit distribution, pyramidal vs. interneuron) | `SuppFig2b.parquet`, `SuppFig2c.parquet` |
| `SupplementaryFigure3.ipynb` | Ext. Data Fig. 3ab (population shock-response heatmap and spatialsocial regression, control/interneuron analysis) | `SuppFig3a.parquet`, `SuppFig3b.parquet` |
| `SupplementaryFigure4.ipynb` | Ext. Data Fig. 4ab (place-field peak rate & spatial information: ShockObs⁺ vs. unresponsive; baseline vs. recall by context) | `SuppFig4a.parquet`, `SuppFig4b.parquet` |
| `SupplementaryFigure5.ipynb` | Ext. Data Fig. 5ac (cross-region SWR interval histograms), 5d (SWR rate by subregion & sleep phase), 5e (per-unit SWR firing rate), 5f (SWR co-activity correlation) | `SuppFig5abc.parquet`, `SuppFig5d.parquet`, `SuppFig5e.parquet`, `SuppFig5f.parquet` |

---

## Data

Summary data tables (one Parquet file per figure panel or panel group) are deposited at [(https://osf.io/7jkn9/overview)].

**Note:** notebooks load their input file(s) with a bare relative filename and no configurable path variable, e.g.:

```python
df = pd.read_parquet('Fig1bc.parquet')
```

To run a notebook, download the file(s) listed for it in the table above and place them in the **same directory as the notebook** (or set that directory as your working directory before launching Jupyter).

| File | Used in |
|---|---|
| `Fig1bc.parquet` | `Figure1.ipynb` |
| `Fig2b.parquet` | `Figure2.ipynb` |
| `Fig2c.parquet` | `Figure2.ipynb` |
| `Fig2d.parquet` | `Figure2.ipynb` |
| `Fig3c.parquet` | `Figure3.ipynb` |
| `Fig4b.parquet` | `Figure4.ipynb` |
| `Fig4c.parquet` | `Figure4.ipynb` |
| `Fig5b.parquet` | `Figure5.ipynb` |
| `Fig5c.parquet` | `Figure5.ipynb` |
| `Fig5d.parquet` | `Figure5.ipynb` |
| `SuppFig1a.parquet`  `SuppFig1g.parquet` | `SupplementaryFigure1.ipynb` |
| `SuppFig2b.parquet`, `SuppFig2c.parquet` | `SupplementaryFigure2.ipynb` |
| `SuppFig3a.parquet`, `SuppFig3b.parquet` | `SupplementaryFigure3.ipynb` |
| `SuppFig4a.parquet`, `SuppFig4b.parquet` | `SupplementaryFigure4.ipynb` |
| `SuppFig5abc.parquet`, `SuppFig5d.parquet`, `SuppFig5e.parquet`, `SuppFig5f.parquet` | `SupplementaryFigure5.ipynb` |

Fig. 5e is computed on the fly from `Fig5d.parquet` (as Δ(shock − safe) explained variance per neuron pair) rather than loaded from a separate file.

---

## Dependencies

The notebooks were developed and executed with **Python 3.10** and require:

```
numpy · pandas · pyarrow · scipy · statsmodels · pingouin · seaborn · matplotlib
```

`pyarrow` (or another Parquet engine, e.g. `fastparquet`) is required for `pandas.read_parquet`.

---

## Contact

Frédéric Michon Linde  michon.f.p@gmail.com  
Christian Keysers  c.keysers@nin.knaw.nl
