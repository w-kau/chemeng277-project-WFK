# chemeng277-project-WFK
CHEMENG 277 Winter 2025 Project - Wylie Kau
wyliekau@stanford.edu

This repository encompasses Wylie Kau's Winter 2025 CHEMENG 277 Final Project. 

The final project paper can be found in the "Final Paper" folder.

The structure of the repository folders: "Data", "Notebooks", and "Outputs" SHOULD NOT BE ADJUSTED in order to ensure reproducibility.

In order to reproduce the results discussed in the paper, run the jupyter notebooks in the "Notebooks" in sequential (chronological) order. The notebook functionality is discussed in brief below:
- "01_FilterAndPreprocessNISTDataset_v3.ipynb" - process and compile the NIST46 dataset into the desired form by downfiltering reports, calculating dG_ion-ligand, performing ion and ligand featurization to generate the dataset used in model training.
- "02_Pipeline_XGBoost_v1.ipynb" - train and evaluate an XGBoost Regressor model to predict dG_ion-ligand based on ion and ligand identity.
- "03_Pipeline_ElasticNet_v1.ipynb" - train and evaluate an ElasticNet Regressor model to predict dG_ion-ligand based on ion and ligand identity.
- "04_ConstructedGDatabase_v3.ipynb" - use a trained XGBoost Regressor model to fill in missing observations in the training dataset and interpolate dG_ion-ligand values to create the "Augmented NIST46 dataset".
- "05_dGTool - XGBoost.ipynb" - a tool built to, given a ligand molecule of interest and a set of ions of interest, query the "Augmented NIST46 dataset" for reports OR if the ligand does not exist in the dataset, generate new dG_ion-ligand predictions for each ion of interest.
- "06_Figure2-Model Comparison.ipynb" - generate a figure directly comparing the out-of-training-set-ligand error and ion-specific error between XGBoost Regressor and ElasticNet Regressor models for, inclusion in the project report.
- "07_Figure3-LFER.ipynb" - apply a linear free energy relationship to the reported/predicted dG_ion-ligand and experimentally observed dG_ion-LFP data for a pyridine molecule and a 4-vinylpyridine functionalized polymer material, for inclusion in the project report.

Package dependencies:
- matplotlib
- numpy
- pandas
- rdkit
- IPython
- pubchempy
- re
- datetime
- pickle
- os
- inpsect
- traceback
- sklearn
- xgboost
