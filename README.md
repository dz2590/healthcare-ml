# Comparative Survival Modeling for Prediction of Incident Myocardial Infarction among ICU Patients

## Overview
This project investigates whether structured clinical data collected during the first 24 hours of an ICU admission can predict the time to a patient's first post-discharge myocardial infarction (MI).

Using the MIMIC-IV database, the project constructs a cohort of adult ICU survivors without prior or index MI history and compares four survival-analysis models:

- Cox Proportional Hazards
- Elastic Net Cox
- Random Survival Forest
- Gradient Boosted Survival

## Repository Structure

```text
.
├── binf_project_code.ipynb
├── bigquery.txt
├── final_report.pdf
└── README.md
```

### `binf_project_code.ipynb`

Contains the end-to-end Python workflow for:
- data loading,
- data cleaning and preprocessing,
- exploratory data analysis,
- feature engineering,
- survival target construction,
- train-test splitting,
- model fitting and hyperparameter tuning 
- model evaluation,
- calibration analysis,
- Kaplan-Meier risk stratification,
- hazard ratio analysis,
- subgroup analysis.

### `bigquery.txt`
Contains the Google BigQuery SQL used to construct the patient cohort and extract clinical features from MIMIC-IV.

### `final_report.pdf`
Contains the full project motivation, literature review, methods, model definitions, performance results, clinical interpretation, limitations, and future work.

## Environment

The notebook uses the following Python packages:

```text
google-cloud-bigquery
pandas
numpy
matplotlib
seaborn
scikit-learn
lifelines
scikit-survival
```

The following installation command can be used: 

```bash
pip install google-cloud-bigquery pandas numpy matplotlib seaborn scikit-learn lifelines scikit-survival
```

Exact reproduction may require an environment compatible with `scikit-survival`, which has compiled dependencies and may be easier to install through Conda.

## Data Access and Reproducibility

This repository does not contain raw MIMIC-IV patient data. Access to MIMIC-IV requires separate authorization through PhysioNet, completion of required training, and acceptance of the dataset's data-use agreement.
 
To reproduce the cohort extraction:

1. Obtain authorized MIMIC-IV access through PhysioNet.
2. Ensure the MIMIC-IV tables are available in Google BigQuery.
3. Configure Google Cloud authentication and billing.
4. Update the destination project and dataset names in `bigquery.txt`.
5. Run the SQL query to create the feature table.
6. Export or load the resulting table into the notebook.
7. Update any local file paths as needed.

The notebook may reference locally generated files such as:

```text
patient_cohort_preprocessed.csv
Saved patient_cohort_preprocessed.csv
table_1_baseline_characteristics.csv
```

## Academic Context and Disclaimer

This project was completed at Columbia University as a survival modeling study using MIMIC-IV clinical data.

This project is for educational purposes only. It is not a validated clinical decision support system and should not be used to guide patient care.


