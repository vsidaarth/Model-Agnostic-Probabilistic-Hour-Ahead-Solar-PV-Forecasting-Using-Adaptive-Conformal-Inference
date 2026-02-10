# Model-Agnostic-Probabilistic-Hour-Ahead-Solar-PV-Forecasting-Using-Adaptive-Conformal-Inference
Code related to the paper titled Model-Agnostic Probabilistic Hour-Ahead Solar PV Forecasting Using Adaptive Conformal Inference

# Hour-Ahead PV Forecasting with Adaptive Conformal Inference

This repository contains the code used in the paper:

"Benchmarking Model Complexity for Hour-Ahead PV Forecasting with Adaptive Conformal Inference"

## Contents
- Data preprocessing
- Deterministic forecasting models (Persistence, ARX, Ridge, DLinear, LSTM)
- Adaptive Conformal Inference (daily reset)
- Evaluation metrics and visualization

## Data
The raw PV dataset cannot be redistributed due to licensing constraints.
The code is written to work with any comparable hourly PV dataset.

## Requirements
See `requirements.txt`.

## Usage
Run the notebook `Energies_Christmas_2025.ipynb` end-to-end to reproduce the experiments.
