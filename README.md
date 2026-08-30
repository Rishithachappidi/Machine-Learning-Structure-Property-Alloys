# Machine Learning-Driven Phase Prediction of High-Entropy Alloys

A machine learning project for predicting the phase structure of **High-Entropy Alloys (HEAs)** using composition and processing-related features.

The project compares multiple supervised learning approaches — **Support Vector Machine (SVM), Random Forest, XGBoost, and Neural Networks** — to investigate their effectiveness in classifying HEA phases such as FCC, BCC, and other phase combinations.

---

## Overview

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

##  Objective

The main objective is to develop and compare machine learning models capable of predicting the **phase structure of High-Entropy Alloys** from their compositional and synthesis-related characteristics.

The project investigates:

1. Which machine learning model performs best for HEA phase prediction?
2. Which alloy descriptors have the greatest influence on phase classification?
3. How well do the models generalize to unseen alloy data?
4. How does class imbalance affect model performance?

---

##  Dataset

The project uses the **HEA Phase Dataset v1d**.

### Dataset Statistics

| Property | Value |
|---|---:|
| Rows | 1,425 |
| Features / Columns | 17 |
| Target Variable | `Phases` |
| Problem Type | Multi-Class Classification |

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

##  Data Preprocessing

The dataset was prepared before model training using the following preprocessing steps:

- Missing-value handling
- Feature selection
- Categorical encoding
- Feature scaling
- Class imbalance handling
- Train-test splitting

**SMOTE (Synthetic Minority Over-sampling Technique)** was used in the relevant model pipeline to address class imbalance.

---

##  Machine Learning Models

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

The RBF kernel allows the model to capture nonlinear relationships between alloy descriptors and phase classes.

---

### 2. Random Forest

A Random Forest Classifier was implemented using an ensemble of decision trees.

Configuration:

    n_estimators = 100
    random_state = 42

Key techniques:

- Data preprocessing
- Feature preparation
- Categorical encoding
- Class balancing
- Random Forest classification
- Feature importance analysis
- Confusion matrix
- Classification report

Random Forest is used to model nonlinear relationships between alloy descriptors and phase structures through an ensemble of decision trees.

---

### 3. XGBoost

**XGBoost (Extreme Gradient Boosting)** was implemented as a gradient-boosting-based classification approach for HEA phase prediction.

Key techniques:

- Data preprocessing
- Feature preparation
- Model training
- Test-set prediction
- Classification report
- Confusion matrix
- Feature importance analysis

XGBoost was included to investigate the effectiveness of gradient-boosted decision trees for learning complex relationships between alloy descriptors and phase classes.

---

### 4. Neural Network

A **Neural Network** was developed for HEA phase classification.

The neural network learns relationships between the processed alloy descriptors and target phase categories.

Key evaluation methods:

- Training performance
- Testing performance
- Classification report
- Confusion matrix
- Feature importance analysis

Training and testing performance are compared to examine the model's ability to generalize to unseen alloy data.

---

##  Model Evaluation

The models were evaluated using multiple classification metrics and analysis techniques.

### Classification Metrics

- Accuracy
- Precision
- Recall
- F1-score

### Confusion Matrix

Confusion matrices were used to analyze:

- Correctly classified samples
- Misclassified samples
- Class-specific prediction behavior
- Confusion between different HEA phase categories

### Feature Importance

Feature importance analysis was performed to investigate which alloy descriptors had the greatest influence on phase classification.

For the SVM model, **Permutation Feature Importance** was used.

---

## Results & Analysis

The project generated detailed training and testing results for all four machine learning models.

The results include:

- Training classification reports
- Testing classification reports
- Training confusion matrices
- Testing confusion matrices
- Feature importance visualizations

The models are compared based on both predictive performance and interpretability.

### Evaluation Criteria

| Evaluation Aspect | Purpose |
|---|---|
| Accuracy | Overall classification performance |
| Precision | Reliability of positive predictions |
| Recall | Ability to identify samples from each class |
| F1-score | Balance between precision and recall |
| Confusion Matrix | Class-level prediction analysis |
| Feature Importance | Influence of alloy descriptors |
| Training vs Testing | Generalization performance |

---

##  Feature Importance Analysis

Feature importance analysis was used to understand which alloy descriptors contribute most strongly to phase prediction.

The analysis considers compositional, thermodynamic, and processing-related features such as:

- `Num_of_Elem`
- `VEC`
- `Atom.Size.Diff`
- `Elect.Diff`
- `dHmix`
- `dSmix`
- `Sythesis_Route`
- `Homog_Temp`
- `Homog_Time`
- `Anneal_Temp`
- `Anneal_Time`
- `Quench_Process`

Different machine learning models provide different mechanisms for evaluating feature influence.

Tree-based models such as Random Forest and XGBoost provide feature-importance measures, while the SVM pipeline uses permutation feature importance.

---

##  Phase Classification

The target variable is:

    Phases

The classification task includes phase categories such as:

- FCC
- BCC
- FCC + BCC
- Other phase combinations present in the dataset

The models learn relationships between alloy descriptors and the observed phase classifications.

---

##  Class Imbalance Handling

The dataset contains an unequal distribution of samples across phase categories.

Class imbalance can cause machine learning models to favor majority classes.

To address this issue, **SMOTE** was incorporated into the relevant model pipeline.

Model performance was also examined using class-specific metrics and confusion matrices rather than relying only on overall accuracy.

---

##  Model Comparison

The four machine learning approaches were compared using multiple evaluation criteria.

| Evaluation Criteria | Purpose |
|---|---|
| Accuracy | Overall classification performance |
| Precision | Reliability of positive predictions |
| Recall | Ability to identify samples from each class |
| F1-score | Balance between precision and recall |
| Confusion Matrix | Class-level prediction behavior |
| Feature Importance | Influence of alloy descriptors |
| Training vs Testing | Generalization performance |

The combination of these evaluation methods provides a broader comparison of the four machine learning approaches.

---

##  Technologies Used

### Programming Language

- Python

### Data Processing

- NumPy
- Pandas

### Machine Learning

- Scikit-learn
- XGBoost
- Support Vector Machine
- Random Forest
- Neural Networks
- SMOTE
- imbalanced-learn

### Visualization

- Matplotlib
- Seaborn

### Evaluation

- Classification Reports
- Confusion Matrices
- Feature Importance
- Permutation Feature Importance





#### Support Vector Machine

    python models/svm.py

#### Random Forest

    python models/randomforest.py

#### XGBoost

    python models/xgboost.py

#### Neural Network

    python models/neuralnetwork.py

---

## Results

The repository contains model-specific result visualizations and classification reports.

### Support Vector Machine

- Training report
- Testing report
- Training confusion matrix
- Testing confusion matrix
- Feature importance

### Random Forest

- Training report
- Testing report
- Training confusion matrix
- Testing confusion matrix
- Feature importance

### XGBoost

- Training report
- Testing report
- Training confusion matrix
- Testing confusion matrix
- Feature importance

### Neural Network

- Training report
- Testing report
- Training confusion matrix
- Testing confusion matrix
- Feature importance

These outputs provide numerical and visual evidence for comparing the four machine learning approaches.

---

##  Key Takeaways

This project demonstrates the application of machine learning to a **materials science classification problem**.

The complete workflow combines:

    Materials Data
          ↓
    Data Preprocessing
          ↓
    Feature Preparation
          ↓
    Machine Learning
          ↓
    HEA Phase Classification
          ↓
    Performance Evaluation
          ↓
    Feature Importance
          ↓
    Model Comparison

The project evaluates not only overall classification performance but also:

- Class-specific prediction behavior
- Training vs testing performance
- Class imbalance
- Feature influence
- Differences between machine learning approaches

---

##  Limitations

The project is based on the **HEA Phase Dataset v1d** and is therefore limited by the size, diversity, and quality of the available data.

Potential limitations include:

- Dataset size
- Unequal phase-class distribution
- Dependence on available alloy descriptors
- Differences in preprocessing requirements between models
- Generalization to HEAs outside the dataset
- Dependence on the quality of the underlying experimental data

The models should therefore be interpreted within the scope of the dataset used for training and evaluation.

---

##  Future Work

Potential extensions of this project include:

- Hyperparameter optimization
- Cross-validation-based model comparison
- Larger and more diverse HEA datasets
- Additional thermodynamic and compositional descriptors
- Advanced ensemble methods
- Explainable AI techniques such as SHAP
- Independent external validation
- Integration with experimental characterization data
- Application to computational alloy screening

---

##  Applications

Machine learning-based HEA phase prediction can support:

- Materials discovery
- Alloy design
- Materials informatics
- Computational materials science
- Candidate alloy screening
- Data-driven materials engineering
- Reduction of experimental search space

The objective is to complement experimental characterization by providing a computational approach for screening and prioritizing candidate alloy compositions.

---

##  Project Information

**Project:** Machine Learning-Driven Phase Prediction of High-Entropy Alloys

**Domain:** Machine Learning · Materials Informatics · Computational Materials Science

**Institution:** Amrita Vishwa Vidyapeetham, Coimbatore

**GitHub:** Rishithachappidi

---

## Conclusion

This project investigates the application of machine learning to **phase prediction in High-Entropy Alloys** using compositional, thermodynamic, and processing-related descriptors.

Four approaches — **SVM, Random Forest, XGBoost, and Neural Networks** — are developed and evaluated using classification metrics, confusion matrices, and feature-importance analysis.

The project demonstrates a complete machine learning workflow from **materials data preprocessing to model development, evaluation, and interpretation**, highlighting the potential of machine learning in **materials informatics and data-driven alloy design**.
