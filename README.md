# Azure_AutoML_Superconductivity
Azure AutoML regression experiment on UCI Superconductivity dataset to predict material conductivity.

# Azure AutoML for Superconductivity Prediction

## Overview
This project demonstrates hands-on experience with Azure Machine Learning's Automated ML (AutoML) for regression tasks. Using the UCI Superconductivity dataset, I configured and ran an AutoML experiment to predict material conductivity based on composition and properties. The goal was to estimate superconductivity critical temperature.

- **Dataset**: [UCI Superconductivity Data Set](https://archive.ics.uci.edu/dataset/464/superconductivty+data) (open-source, 21,263 samples, 81 features).
- **Azure Services Used**: Azure ML Workspace, AutoML for regression, compute cluster.
- **Key Steps**:
  1. Uploaded and verified dataset columns in Azure ML.
  2. Configured AutoML: Regression task, target = critical temperature (conductivity proxy), imputed missing values with defaults, no high cardinality issues.
  3. Ran experiment for 6 hours 15 minutes on standard compute.
- **Results**: Best model was a VotingEnsemble with Root Mean Squared Error (RMSE) of 0.033. Full metrics and child runs reviewed in Azure portal.

This showcases Azure ML's ability to automate model selection and hyperparameter tuning for materials science applications.

## Setup and Replication
To replicate (in your own Azure subscription):
1. Create an Azure ML workspace.
2. Upload the dataset (see /data/sample_superconductivity.csv for preview).
3. Use Azure ML Studio to create an AutoML job with similar config.
