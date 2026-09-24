# Model-Agnostic Hour-Ahead PV Forecasting with Adaptive Conformal Inference

[![DOI](https://img.shields.io/badge/DOI-10.3390%2Fen19061495-blue)](https://doi.org/10.3390/en19061495)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0--1.0-lightgrey.svg)](LICENSE)

Research code accompanying the paper:

> V. Suresh, “Model-Agnostic, Probabilistic, Hour-Ahead Solar PV Forecasting Using Adaptive Conformal Inference,” *Energies*, vol. 19, no. 6, article 1495, 2026. https://doi.org/10.3390/en19061495

## Overview

This repository contains an end-to-end implementation for comparing deterministic hour-ahead photovoltaic (PV) power forecasters and calibrating each of them with Adaptive Conformal Inference (ACI). The same evaluation framework is applied to persistence, ARX, ridge regression, DLinear, and LSTM models. A daily reset of the adaptive miscoverage state is used to respect the day–night structure of PV generation.

The central research question is whether greater point-model complexity still provides a practical advantage after all models receive the same adaptive uncertainty calibration.

## Scientific contribution

- A model-agnostic ACI framework spanning persistence, statistical, linear, and deep-learning forecasters.
- A common comparison of deterministic accuracy, probabilistic reliability, interval sharpness, and computational cost.
- A PV-specific daily reset of the adaptive miscoverage state.
- Evidence that simple forecasters can achieve probabilistic reliability close to deep models after comparable calibration.

## Models and evaluation

**Point forecasters:** Persistence, ARX, ridge regression, DLinear, and vanilla LSTM.

**Uncertainty quantification:** ACI with a daily reset.

**Reported measures:** RMSE, MAE, empirical prediction-interval coverage, mean interval width, CRPS, Winkler score, and computation time.

## Main results

Among the point models tested in the study, LSTM achieved the best deterministic performance with an RMSE of **0.336 kW** and an MAE of **0.164 kW**. After ACI calibration, all tested model classes achieved closely grouped empirical coverage of approximately **90.8–91.4%**. The result shows that stronger point accuracy does not automatically translate into a proportionally large advantage in calibrated probabilistic reliability.

These values refer to the experimental setting reported in the paper; consult the article for the complete protocol, tables, and interpretation.

## Repository contents

| File | Purpose |
| --- | --- |
| **Full forecasting + ACI pipeline.ipynb** | Data preprocessing, deterministic forecasting, daily-reset ACI, evaluation, and visualization |
| **requirements.txt** | Python dependencies |
| **LICENSE** | CC0 1.0 Universal license |

## Data availability

The raw PV dataset cannot be redistributed because of licensing constraints. To run the workflow, provide a comparable hourly PV dataset and adjust the input path and column mapping in the notebook. The paper is the authoritative source for the data description and experimental protocol.

## Reproducing the workflow

1. Clone or download this repository.
2. Create a Python environment and install the packages listed in **requirements.txt**.
3. Place an appropriately structured hourly PV dataset in an accessible location.
4. Open **Full forecasting + ACI pipeline.ipynb** and update the data path and column mapping.
5. Run the notebook cells in order.

Random initialization, library versions, and hardware can lead to small numerical differences.

## Citation

If this repository supports your work, please cite:

~~~bibtex
@article{suresh2026modelagnostic,
  author  = {Suresh, Vishnu},
  title   = {Model-Agnostic, Probabilistic, Hour-Ahead Solar PV Forecasting Using Adaptive Conformal Inference},
  journal = {Energies},
  volume  = {19},
  number  = {6},
  pages   = {1495},
  year    = {2026},
  doi     = {10.3390/en19061495}
}
~~~

## License

This repository is released under the [CC0 1.0 Universal license](LICENSE). Please cite the associated paper when using the research implementation or results.
