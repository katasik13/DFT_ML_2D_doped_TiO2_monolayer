# Formation energy predictions for 2D doped TiO<sub>2</sub> monolayer

This repo is associated with the paper *Data-Efficient Machine Learning for predicting dopant formation energies in TiO<sub>2</sub> monolayer*, in which we construct a DFT dataset for 2D doped TiO<sub>2</sub> monolayers and examine the machine learning performance in the small-data regime.

Preprint is available in arXiv: arXiv:2602.14650 [cond-mat.mtrl-sci] 

Manuscript under review (Feb 2026)

## Datasets
The datasets list Pt-doped (84 data points) and Ag-doped (14 data points) monolayer configurations by labels (Configuration_1, Configuration_2,...). Dopant concentration of each configuration is indicated, and the associated calculated propeties are provided. Feature descriptions are included here and can also be found in the Supplementary information accompanying the paper.

The Pt-doped and Ag-doped datasets are available in separate CSV files. For the Pt-doped configurations, the same CSV file contains both the original dataset (57 configurations, corresponding to the dataset "before data addition") and expanded dataset (84 configurations in total, corresponding to the dataset "after data addition"; obtained by adding 27 configurations). The configurations are ordered such that the first 57 entries in the CSV file corresponds to the original dataset, while the subsequent entries correspond to the additional configurations. For the ML predictions, the appropriate dataset were selected programmatically, with the corresponding implementation provided in the python script. The data file includes a "split" column indicating training and test usage of each configuration. 5-fold cross-validation was performed excusively on the training subset.

For both Pt-doped and Ag-doped datasets, the 6 eV criterion was applied prior to dataset construction. Configurations not satisfying this criterion were removed directly, such that all configurations included in the provided files have already been pre-filtered.

Example of the supercell of a doped configuration, where the properties are calculated:

![Schematic illustartion of the supercell of a doped configuration, where the properties are calculated.](Datasets/Example_structure.png)

## Codes
Jupyter notebooks are provided for feature analysis (including Pearson correlation analysis, SHAP analysis, multicollinearity assessment, and recursive feature elimination step) and for ML predictions (including data preparation, training, predictions, and cross-validation). Separate notebooks are available for Pt-only and Pt+Ag datasets. 

