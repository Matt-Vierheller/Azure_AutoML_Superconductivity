# Azure AutoML: Predicting Superconductor Critical Temperature

## Project Overview
Hands-on Azure Machine Learning AutoML regression experiment using the UCI Superconductivity dataset. Goal: Predict the critical temperature (in Kelvin) at which a material becomes superconducting, based on 81 composition-derived features.

- **Dataset**: [UCI Superconductivity Data](https://archive.ics.uci.edu/dataset/464/superconductivty+data)  
  - 21,263 samples  
  - 81 features (e.g., statistical aggregates of atomic mass, valence, thermal conductivity, etc.) + target `critical_temp`  
  - Open-source, no missing values in original data  
  - Sample preview in `/data/sample_superconductivity.csv`

- **Azure Tools Used**: Azure ML Studio (UI-driven), AutoML for regression, compute resources.

- **Process**:
  1. Uploaded dataset and verified columns/data sample.
  2. Configured AutoML job: Regression task, target = `critical_temp`.
  3. Enabled default featurization (imputed any missing if needed—none detected; no high cardinality features).
  4. Ran experiment (~6 hours 15 minutes total runtime).

- **Key Result**: Best model = **VotingEnsemble** with **RMSE = 0.033** (excellent fit for this physics dataset—ensembles often excel on complex material properties).

## Visual Proof from Azure ML Studio

**Data Sample & Column Verification**  
![Data Sample](images/data_sample.png)

**AutoML Configuration Settings**  
![Configuration](images/configuration_settings.png)

**Experiment Runtime & Overview**  
![Time and Date / Run Details](images/time_and_date.png)

**Ranked Models**  
![Models List](images/models.png)

**Best Model Score & Details (VotingEnsemble)**  
![Score and Model](images/score_and_model.png)

**Run Metrics for Best Model**  
![Metrics](images/run_metrics.png)

## Results Summary
- **Primary Metric Achieved**: Root Mean Squared Error = 0.033  
- **Model Type**: VotingEnsemble (combines multiple algorithms for robustness)  
- **Insights**: AutoML automatically tested dozens of models/params; ensemble won, showing value of automated exploration in materials prediction.

## Learnings & Why This Matters
- Navigated Azure ML Studio end-to-end without code.
- Managed long-running jobs (monitored progress/costs via free credits).
- Interpreted scientific ML results (low RMSE indicates reliable predictions for superconductivity research/applications).

To replicate: Sign into Azure ML Studio, create a workspace, upload the UCI dataset, and configure a similar AutoML regression job.

Questions? Feel free to open an issue or connect on LinkedIn/X (@Mvierhe1).

MIT License – feel free to reference!
