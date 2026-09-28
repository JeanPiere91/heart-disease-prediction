# Heart Disease Prediction

## Reproducing and Improving Heart Disease Prediction: A Duplicate-Aware Machine Learning Evaluation

**Student:** Jean Bellota  
**Student ID:** s225462019  
**Unit:** SIT720 - Machine Learning  
**Task:** 11.1HD - Machine Learning Research  
**Deakin University**

---

## Project Overview

This project reproduces and critically evaluates machine learning methods for heart disease prediction based on the study:

> M. Bhagat, A. Sharma, and P. Agarwal,  
> "An efficient stacking-based ensemble technique for early heart attack prediction,"  
> *Multimedia Tools and Applications*, vol. 84, pp. 36351–36375, 2025.

The original study evaluates several machine learning classifiers and proposes a stacking ensemble for heart disease prediction.

This reproduction investigates the reported performance and examines the effect of duplicate observations on model evaluation. A duplicate-aware machine learning pipeline is then developed using repeated cross-validation, feature selection, hyperparameter optimisation, and nested cross-validation.

---

## Research Objectives

The main objectives of this project are to:

- Reproduce the machine learning experiments from the selected research paper.
- Evaluate Logistic Regression, Naive Bayes, K-Nearest Neighbours, Decision Tree, Random Forest, XGBoost, and Stacking.
- Investigate data quality and duplicate observations in the dataset.
- Examine the effect of duplicate removal on model performance.
- Evaluate feature selection and Random Forest hyperparameter optimisation.
- Develop a more rigorous evaluation protocol using nested cross-validation.
- Compare the published results, reproduced results, and proposed duplicate-aware approach.

---

## Dataset

The project uses the Heart Disease Dataset containing **1,025 observations**, 13 predictor variables, and one target variable.

During the data-quality analysis, the dataset was found to contain:

- **1,025 total observations**
- **302 unique observations**
- **723 duplicate rows**

In the conventional 80/20 reproduction split, **98.54% of test observations had an identical record in the training set**.

For this reason, duplicate removal was incorporated into the proposed evaluation methodology.

---

## Machine Learning Models

The following classifiers were evaluated:

- Logistic Regression
- Gaussian Naive Bayes
- K-Nearest Neighbours
- Decision Tree
- Random Forest
- XGBoost
- Stacking Ensemble

The proposed solution focuses on a duplicate-aware Random Forest pipeline evaluated using nested cross-validation.

---

## Proposed Methodology

The proposed workflow consists of:

1. Data quality analysis
2. Exact duplicate detection and removal
3. Duplicate-free model evaluation
4. Repeated Stratified Cross-Validation
5. Mutual Information feature selection experiment
6. Random Forest hyperparameter optimisation
7. Nested Cross-Validation
8. Final comparison with the published and reproduced results

Nested cross-validation is used for the final evaluation to separate hyperparameter selection from performance estimation.

---

## Key Results

The conventional reproduction produced extremely high performance, including perfect scores for the reproduced stacking ensemble.

After removing duplicate observations and applying a more rigorous evaluation protocol, the final nested cross-validation Random Forest achieved:

| Metric | Mean | Standard Deviation |
| --- | ---: | ---: |
| Accuracy | 0.8181 | 0.0488 |
| Precision | 0.8200 | 0.0536 |
| Recall | 0.8598 | 0.1083 |
| F1-score | 0.8349 | 0.0522 |
| AUC | 0.9145 | 0.0176 |

The results demonstrate that the main contribution of the proposed workflow is not simply achieving higher accuracy, but providing a more rigorous and duplicate-aware estimate of model generalisation.

---

## Project Structure

```text
heart-disease-prediction/
│
├── data/
│   └── heart.csv
│
├── notebook/
│   └── SIT720_11_1HD_Jean_Bellota.ipynb
│
├── results/
│   ├── final_comparison.csv
│   ├── nested_cv_folds.csv
│   ├── nested_cv_summary.csv
│   ├── feature_selection_results.csv
│   └── rf_optimisation_comparison.csv
│
├── requirements.txt
└── README.md
```

---

## Requirements

The project was implemented in Python using Jupyter Notebook.

The main libraries used include:

- pandas
- NumPy
- Matplotlib
- scikit-learn
- XGBoost

The complete list of required Python packages is provided in:

```text
requirements.txt
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/JeanPiere91/heart-disease-prediction
```

Move into the project directory:

```bash
cd heart-disease-prediction
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

---

## Running the Experiment

Open Jupyter Notebook or JupyterLab from the project directory:

```bash
jupyter notebook
```

Then open:

```text
notebook/SIT720_11_1HD_Jean_Bellota.ipynb
```

Run the notebook sequentially from beginning to end.

The notebook performs the complete experimental workflow, including:

- Dataset loading
- Data-quality analysis
- Duplicate detection
- Published experiment reproduction
- Individual classifier evaluation
- Stacking ensemble reproduction
- Duplicate-free evaluation
- Repeated cross-validation
- Feature selection
- Random Forest hyperparameter optimisation
- Nested cross-validation
- Final model comparison
- Export of experimental results

The principal experimental outputs are automatically saved in the `results/` directory.

---

## Results Directory

The `results/` directory contains the principal outputs generated by the notebook:

```text
results/
├── final_comparison.csv
├── nested_cv_folds.csv
├── nested_cv_summary.csv
├── feature_selection_results.csv
└── rf_optimisation_comparison.csv
```

These files provide the numerical results used for the final analysis and comparison presented in the report.

---

## Reproducibility

Random seeds are defined throughout the experimental workflow where applicable to improve reproducibility.

The final evaluation uses nested cross-validation, where:

- The **outer cross-validation loop** estimates model performance.
- The **inner cross-validation loop** performs hyperparameter optimisation.

This separation reduces the risk of using the same validation information for both model selection and final performance estimation.

To reproduce the results, run the notebook from the first cell to the final cell without changing the dataset or experimental configuration.

---

## Video Presentation

The video presentation demonstrates the research reproduction, implementation, proposed methodology, experimental results, and main limitations.

**Video:** [Youtube Video](https://youtu.be/904DTdRp1FY)

---

## Main Conclusion

The conventional reproduction initially produced results close to or higher than those reported in the selected study, including perfect performance for the reproduced stacking ensemble.

However, the data-quality analysis identified extensive duplication in the available dataset. Of the 1,025 observations, only 302 were unique, and the conventional random train-test split resulted in substantial overlap between training and testing observations.

After removing exact duplicates, the estimated performance became substantially more conservative.

The final nested cross-validation Random Forest achieved an average **Accuracy of 0.8181**, **F1-score of 0.8349**, and **AUC of 0.9145**.

The main contribution of the proposed workflow is therefore not a universally higher classification score, but a more rigorous separation of data-quality assessment, model optimisation, and final performance estimation.

The relatively small number of unique observations remains an important limitation, and external validation would be necessary before considering clinical deployment.

---

## Reference

M. Bhagat, A. Sharma, and P. Agarwal, "An efficient stacking-based ensemble technique for early heart attack prediction," *Multimedia Tools and Applications*, vol. 84, pp. 36351–36375, 2025, doi: 10.1007/s11042-024-19293-7.

---

## Generative AI Acknowledgement

Generative AI was used to assist with language editing and to improve the clarity and professional presentation of the project documentation.