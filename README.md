# Diagnosing SHAP Attributions on a Benchmark Airline Satisfaction Survey

Code and saved results for the paper *Diagnosing SHAP Attributions on a Benchmark Airline Satisfaction Survey: Rating-Level Patterns, Travel Purpose and Dataset Artefacts* by Sara Mohammed Meraj Zaki (Department of Computer Science, Gulf University for Science and Technology, Kuwait).

The study compares four classifiers under leakage-controlled cross-validation on the public Airline Passenger Satisfaction survey (129,880 passengers), describes out-of-fold SHAP attributions by rating level and travel purpose, tests them with interventional and probability-scale SHAP, TreeSHAP interaction values, reweighting, covariate standardisation, 5 × 5 repeated cross-validation and refits, and compares them with the raw data and with independent Skytrax reviews. The strongest patterns are stable under every check but trace back to near-deterministic rules in the data file.

## Contents

| Path | Contents |
|---|---|
| `Airline_Satisfaction_SHAP_Diagnostics.ipynb` | The complete analysis (sections 1–5) |
| `results/` | Every table and array the notebook saves |
| `figures/` | Figs. 1–3 of the paper (600 dpi) |
| `requirements.txt` | Package versions used |

## How to reproduce

1. Install Python 3.13 and `pip install -r requirements.txt`.
2. Download `airline_passenger_satisfaction.csv` from https://www.kaggle.com/datasets/mysarahmadbhat/airline-passenger-satisfaction and place it next to the notebook. It is record-for-record identical to Klein's 2020 version (https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction) apart from renamed category labels.
3. For section 5, download `data/airline.csv` from https://github.com/quankiquanki/skytrax-reviews-dataset and save it as `skytrax_airline.csv`.
4. Run all cells in order. No GPU is needed; seeds are fixed (42). Interventional SHAP, interaction values and the repeated cross-validation are slow on a CPU (roughly 1–2 hours in total) and cache their results in `results/`.
