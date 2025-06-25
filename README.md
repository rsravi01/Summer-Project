# 🐞 Software Bug Prediction using Semi-Supervised Learning

This project implements a semi-supervised learning approach to predict software bugs using the KC1 defect dataset from the PROMISE repository. It combines ensemble models with pseudo-labeling to leverage both labeled and unlabeled data, improving prediction performance under limited supervision.

---

## 🚀 Overview

- Developed a **semi-supervised machine learning pipeline** to detect defects in software modules.
- Applied **SMOTE** to handle class imbalance and **StandardScaler** for feature normalization.
- Used **Random Forest feature importance** for feature selection, achieving 88% accuracy on selected features.
- Combined **Random Forest, XGBoost, SVM, and Logistic Regression** in a soft-voting ensemble.
- Employed **iterative pseudo-labeling** with confidence thresholds (0.80–0.90) and **early stopping** based on validation F1-score stagnation.

---

## 🧱 System Architecture

The following pipeline summarizes the semi-supervised defect prediction architecture:

<📄 Data Input
   │
   ▼
🧪 Preprocessing
(StandardScaler + SMOTE)
   │
   ▼
📊 Feature Selection
(Random Forest Feature Importance)
   │
   ▼
🔁 Iterative Training Loop
   │
   ├──► Train Ensemble Model
   │       ├── Random Forest
   │       ├── XGBoost
   │       ├── SVM
   │       └── Logistic Regression
   │
   ├──► Predict Unlabeled Samples
   ├──► Select High-Confidence Pseudo Labels (Threshold: 0.80–0.90)
   └──► Augment Training Set
   │
   ▼
⏹ Early Stopping
(Monitor Validation F1 Stagnation)
   │
   ▼
✅ Final Evaluation
(Accuracy, Precision, Recall, F1-Score)
>
![SummerProject](https://github.com/user-attachments/assets/97ebaa9e-983c-44f5-8d5d-6148867102f3)
![SummerProject](https://github.com/user-attachments/assets/97ebaa9e-983c-44f5-8d5d-6148867102f3)
![SummerProject](https://github.com/user-attachments/assets/894fe6f8-3778-4890-8941-129ad35d6d71)
![SummerProject](https://github.com/user-attachments/assets/894fe6f8-3778-4890-8941-129ad35d6d71)




## 📊 Results

- Explored labeled data ratios from **10% to 90%**.
- Achieved peak test performance:
  - **Accuracy:** 88.44%
  - **F1-Score:** 0.8451
  - **Precision:** 0.8491
  - **Recall:** 0.8411
- Demonstrated strong generalization using semi-supervised learning under label-scarce conditions.

---

## 🧰 Tools & Technologies

- **Languages**: Python
- **Libraries**:  
  - `scikit-learn` (RandomForest, SVC, LogisticRegression, StandardScaler, metrics)  
  - `XGBoost`  
  - `imbalanced-learn` (SMOTE)  
  - `Pandas`, `NumPy`  
  - `VotingClassifier`

---

## 🗂 Dataset

- **KC1** defect dataset from the [PROMISE repository](http://promise.site.uottawa.ca/SERepository/datasets-page.html)
- Preprocessing steps:
  - Handling missing values
  - Feature normalization
  - Binary classification based on `defects` field

---

## 🧠 Methodology

1. **Preprocessing**  
   Normalize and balance data using `StandardScaler` and `SMOTE`.

2. **Feature Selection**  
   Use Random Forest importance scores to select top predictors.

3. **Model Training**  
   Train ensemble on labeled samples using soft-voting.

4. **Pseudo-labeling**  
   Add confidently predicted unlabeled samples (≥ threshold) to the training set iteratively.

5. **Early Stopping**  
   Monitor validation F1; stop if no improvement in 3 epochs.

6. **Evaluation**  
   Assess final model using test set performance metrics.

---

## 📁 Files

- `software_bug_prediction.py`: Full implementation.
- `kc1.csv`: Input dataset.
- `README.md`: Documentation.

---

## 🙏 Acknowledgements

This project was conducted under the guidance of **Ms. Vandana Bhattacharya** as part of the **Summer Training Program** at *Birla Institute of Technology, Mesra*.  
We are thankful to the **PROMISE repository** for providing access to the KC1 software defect dataset used in this work.


