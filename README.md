# Machine Learning-Driven Phase Prediction of High-Entropy Alloys

A machine learning project for predicting the phase structure of **High-Entropy Alloys (HEAs)** using composition and processing-related features.

The project compares multiple supervised learning approaches — **Support Vector Machine (SVM), Random Forest, XGBoost, and Neural Networks** — to investigate their effectiveness in classifying HEA phases such as FCC, BCC, and other phase combinations.

---

## 📌 Overview

High-Entropy Alloys (HEAs) are advanced metallic materials composed of multiple principal elements. Their resulting phase structure plays an important role in determining their material behavior and performance.

Traditional identification of alloy phases often requires experimental characterization techniques, which can be time-consuming and expensive.

This project explores the use of **Machine Learning (ML)** to predict HEA phase structures from available alloy descriptors and processing information.

The workflow includes:

- Dataset preprocessing
- Feature selection
- Categorical encoding
- Missing-value handling
- Feature scaling
- Class imbalance handling
- Model training
- Model evaluation
- Feature importance analysis
- Confusion matrix analysis
- Model comparison

---

## 🎯 Objective

The main objective is to develop and compare machine learning models capable of predicting the **phase structure of High-Entropy Alloys** from their compositional and synthesis-related characteristics.

The project investigates:

1. Which machine learning model performs best for HEA phase prediction?
2. Which alloy descriptors have the greatest influence on phase classification?
3. How well do the models generalize to unseen alloy data?
4. How does class imbalance affect model performance?

---

## 📊 Dataset

The project uses the **HEA Phase Dataset v1d**.

### Dataset Statistics

- **Rows:** 1,425
- **Features/Columns:** 17
- **Target:** `Phases`

### Major Features

| Feature | Description |
|---|---|
| `Num_of_Elem` | Number of elements in the alloy |
| `VEC` | Valence Electron Concentration |
| `Atom.Size.Diff` | Atomic size difference |
| `Elect.Diff` | Electronegativity difference |
| `dHmix` | Enthalpy of mixing |
| `dSmix` | Entropy of mixing |
| `Sythesis_Route` | Alloy synthesis route |
| `Homog_Temp` | Homogenization temperature |
| `Homog_Time` | Homogenization time |
| `Anneal_Temp` | Annealing temperature |
| `Anneal_Time` | Annealing time |
| `Quench_Process` | Quenching process |
| `Phases` | Target phase classification |

Some metadata and processing columns were excluded during individual model pipelines where they were not considered relevant.

---

## 🧠 Machine Learning Models

Four machine learning approaches were investigated.

### 1. Support Vector Machine

An SVM classifier using an **RBF kernel** was developed for phase classification.

Key techniques:

- StandardScaler
- Label Encoding
- Train-test split
- SMOTE for class balancing
- Permutation feature importance
- Confusion matrix
- Classification report

---

### 2. Random Forest

A Random Forest Classifier was implemented using an ensemble of decision trees.

Configuration:

```text
n_estimators = 100
random_state = 42
```
