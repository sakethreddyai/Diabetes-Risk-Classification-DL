# Diabetes Risk Classification Using Deep Learning

A deep learning project exploring diabetes classification through neural networks, hyperparameter optimisation, and subgroup performance analysis.

## Overview

This project investigates how neural network architectures and training configurations affect diabetes classification performance. It includes experiments with different model architectures, optimisers, batch sizes, and training durations, alongside an analysis of performance across BMI and physical activity subgroups.

The project also explores an important question in human-centred machine learning: **Does a model perform consistently across different population subgroups?**

## Project Objectives

- Develop a neural network for diabetes classification.
- Experiment with network architectures and training configurations.
- Compare model performance using cross-validation.
- Examine reported performance differences across BMI and physical activity subgroups.
- Explore the limitations of using a single overall accuracy score to evaluate a classification model.

## Repository Structure

```text
Diabetes-Risk-Classification-DL/
├── main.ipynb          # Main classification experiments
├── grid search.ipynb   # Hyperparameter search experiments
├── main.pdf            # Main project report
├── grid search.pdf     # Hyperparameter search report
├── dataset.csv         # Dataset used for experimentation
└── best_model.h5       # Saved model
```

## Methodology

The project follows an experimental deep learning workflow:

1. **Data preparation** — prepare the dataset for model training.
2. **Neural network development** — experiment with a multilayer neural network.
3. **Hyperparameter optimisation** — investigate different batch sizes, optimisers, training durations, and network configurations.
4. **Model evaluation** — assess classification performance using the evaluation procedures described in the reports.
5. **Subgroup analysis** — investigate differences in reported performance across BMI and physical activity categories.

## Model Configuration

The project reports the following best-performing configuration from its hyperparameter search:

| Parameter | Reported configuration |
|---|---|
| Hidden-layer architecture | `[32, 16, 8]` |
| Optimiser | Adam |
| Batch size | 256 |
| Training epochs | 30 |
| Cross-validation accuracy | 74.84% ± 0.34 percentage points |

These figures are reported experimental results and have not been independently revalidated. Cross-validation accuracy should not be interpreted as held-out test accuracy.

## Subgroup Performance Analysis

The report presents the following subgroup accuracy results:

| Subgroup | Reported accuracy |
|---|---:|
| Low BMI | 71.19% |
| High BMI | 42.53% |
| Inactive | 38.87% |
| Active | 55.08% |

These results motivate further investigation into subgroup performance and model reliability.

Accuracy alone does not establish whether a model is fair or clinically reliable. A more complete assessment would require subgroup sample sizes, confusion matrices, recall, false-negative rates, and consistent evaluation procedures.

## Technologies

- **Python**
- **Jupyter Notebook**
- **TensorFlow / Keras**
- **NumPy and pandas**
- **Scikit-learn**
- **Matplotlib** (where used in the notebooks)

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/sakethreddyai/Diabetes-Risk-Classification-DL.git
cd Diabetes-Risk-Classification-DL
```

### 2. Set up an environment

Create and activate a Python virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install the libraries required by the notebooks. The exact package versions should be confirmed from the original environment before attempting to reproduce the reported results.

```bash
pip install jupyter pandas numpy scikit-learn matplotlib tensorflow
```

### 3. Run the notebooks

Start Jupyter:

```bash
jupyter notebook
```

Open `main.ipynb` for the primary experiments or `grid search.ipynb` for the hyperparameter search.

The saved model is provided as `best_model.h5`. Compatibility may depend on the TensorFlow/Keras version used to create it.

## Limitations and Future Work

Potential improvements include:

- Preventing data leakage by fitting preprocessing steps only on training data.
- Establishing a consistent train, validation, and test split.
- Keeping the test set separate from model selection and hyperparameter tuning.
- Reporting precision, recall, F1-score, ROC-AUC, and confusion matrices.
- Evaluating subgroup sample sizes and false-negative rates.
- Documenting package versions, random seeds, and reproducible training procedures.

These steps would help establish how robust the reported results are beyond the original experiments.

## Responsible Use

This is an academic machine learning project intended for experimentation and learning. It is **not a clinically validated diagnostic tool** and should not be used to diagnose diabetes or guide medical decisions.

## Author

**Saketh Reddy**

GitHub: [@sakethreddyai](https://github.com/sakethreddyai)
