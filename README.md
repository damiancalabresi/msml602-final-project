# Final Project

## Stages

Deadline | Stage | Status
--- | --- | ---
03/13 | Dataset extraction and research | Done
03/20 | Data cleanup and EDA | Done
03/27 | Identify scope. Comprehensive Analysis of Democracy Indexes | Done
04/03 | Cleanup and Merge Datasets | Done
04/10 | Linear and Logistic Regression | Done
04/17 | SVM and Clustering | Done
04/24 | Identify Outliers | Done
05/01 | Analyze impact of global events | Out of Scope
05/08 | Draft paper | Pending
05/15 | Redact paper and review | Pending

## 1 - Dataset Extraction, Cleanup, and Research

### Goal

Transform all the raw datasets from complex Excel or Data files to CSV files. Normalize the column names and remove unnecessary columns.

Shift time series data to have years as rows.

Document and describe the meaning of each column/predictor.

Fix empty rows and NaN values.

Descriptive analysis of the datasets, define scope and properties to analyze.

See [1-dataset-cleanup/README.md](1-dataset-cleanup/README.md) for details.

See [1-dataset-cleanup/dataset-extraction.ipynb](1-dataset-cleanup/dataset-extraction.ipynb) for the code.

## 2 - EDA and Scope Definition

See [2-eda-scope-definition/README.md](2-eda-scope-definition/README.md) for details.

For the code, see:
- [pca-polity5.ipynb](2-eda-scope-definition/pca-polity5.ipynb)
- [pca-freedom-in-the-world.ipynb](2-eda-scope-definition/pca-freedom-in-the-world.ipynb)
- [pca-lied.ipynb](2-eda-scope-definition/pca-lied.ipynb)
- [pca-global-religious-diversity.ipynb](2-eda-scope-definition/pca-global-religious-diversity.ipynb)
- [pca-national-religion-dataset.ipynb](2-eda-scope-definition/pca-national-religion-dataset.ipynb)
- [pca-georgetown.ipynb](2-eda-scope-definition/pca-georgetown.ipynb)
- [pca-world-bank.ipynb](2-eda-scope-definition/pca-world-bank.ipynb)

## 3 - Merge and Compare Linear Regression

See [3-merge-compare-linear-regression/README.md](3-merge-compare-linear-regression/README.md) for details.

For the code, see:
- [women-rights-and-democracy.ipynb](3-merge-compare-linear-regression/women-rights-and-democracy.ipynb)
- [compare-democracy-indexes.ipynb](3-merge-compare-linear-regression/compare-democracy-indexes.ipynb)