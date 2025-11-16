### Project Overview

This project aims to predict the quality rating of red wine based on its physicochemical characteristics (features) using machine learning classification models. The quality scores range from 3 to 8.

### Dataset

* **Source:** Kaggle Wine Quality Dataset (WineQT.csv)
* **Total Samples:** 1143
* **Target Variable (Y):** `quality` (Quality rating: 3, 4, 5, 6, 7, 8)
* **Features (X) Used:**
    * fixed acidity
    * volatile acidity
    * citric acid
    * chlorides
    * total sulfur dioxide
    * sulphates
    * alcohol

### Data Preprocessing and Preparation

1.  **Data Cleaning:** The dataset was checked and found to have no missing values.
2.  **Feature Selection:** The 7 physicochemical characteristics listed above were selected as model inputs.
3.  **Data Splitting:** The dataset was split into training and testing sets with a 9:1 ratio (`test_size=0.1`). Stratified sampling (`stratify`) was used to ensure consistent distribution of quality levels in both sets.

### Model Implementation and Evaluation

The project implements and compares three machine learning classification models:



#### 1. Decision Tree

* **Model Class:** `sklearn.tree.DecisionTreeClassifier`.
* **Implementation Details:** A simple and highly interpretable tree-based structure for classification.
* **Evaluation Metrics:** Accuracy, Classification Report, Confusion Matrix.

#### 2. Random Forest

* **Model Class:** `sklearn.ensemble.RandomForestClassifier`.
* **Implementation Details:** An ensemble learning method that builds multiple Decision Trees and aggregates their results to improve robustness and accuracy.
* **Evaluation Metrics:** Accuracy, Classification Report, Confusion Matrix.

#### 3. Support Vector Machine (SVM)

* **Model Class:** `sklearn.multiclass.OneVsRestClassifier` combined with `SVC`.
* **Kernel:** Radial Basis Function (RBF kernel).
* **Imbalance Handling:** The `class_weight="balanced"` parameter was set in the `SVC` to address potential class imbalance among quality levels.
* **Evaluation Metrics:** Accuracy, Classification Report, Confusion Matrix.

### System Requirements

* Python 3.10.0
* pandas
* scikit-learn (sklearn)
* kagglehub (for data download)
* Other libraries for visualization (e.g., matplotlib, seaborn)