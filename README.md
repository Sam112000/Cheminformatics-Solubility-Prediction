# Cheminformatics: In-Silico Prediction of Aqueous Solubility

## Overview
A cheminformatics project reproducing the well-known ESOL solubility
prediction study (Delaney, 2004), applying molecular descriptor calculation
and machine learning to predict aqueous solubility (logS) of small molecules.
Inspired by a public tutorial approach to this classic problem, adapted and
extended with automated model comparison and tuning.

## Contents
- **Part 1** — Descriptor calculation: computes molecular descriptors
  (MolLogP, molecular weight, number of rotatable bonds, aromatic
  proportion) from SMILES using RDKit, based on the Delaney solubility
  dataset
- **Part 2.1** — Feature preparation: generates the final descriptor-based
  dataset (`delaney_solubility_with_descriptors.csv`) used for modeling
- **Part 2.2** — Model building with PyCaret: automated comparison of
  regression models, selection and tuning of the best-performing model

## Methods
- Tools: Python, RDKit, PyCaret (regression module)
- Calculated 4 molecular descriptors per compound (MolLogP, MolWt,
  NumRotatableBonds, AromaticProportion)
- Used PyCaret's `compare_models()` to benchmark multiple regression
  algorithms on an 80/20 train/holdout split
- Selected and tuned an Extra Trees Regressor (`tune_model`, 50 iterations,
  optimized for MAE)

## Results
- Best model: Extra Trees Regressor
- Holdout set performance: **R² = 0.867, MAE = 0.527, RMSE = 0.735**

## What I learned
- End-to-end molecular descriptor engineering with RDKit
- Automated model selection and hyperparameter tuning with PyCaret
- Practical evaluation of regression models on a real cheminformatics
  benchmark dataset

## References
1. Delaney, J.S. "ESOL: Estimating Aqueous Solubility Directly from
   Molecular Structure." *J. Chem. Inf. Comput. Sci.* 2004, 44, 3, 1000-1005.
2. Walters, P. "Predicting Aqueous Solubility – It's Harder Than It Looks."
   *Practical Cheminformatics Blog*, 2018.

## Status
Independent reproduction of a published benchmark study, extended with
automated ML model comparison and tuning.
