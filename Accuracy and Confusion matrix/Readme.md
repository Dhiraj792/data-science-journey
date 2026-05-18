# 📊 Accuracy, Precision, Recall & F1-Score in Machine Learning

This project demonstrates the practical implementation of important Machine Learning classification evaluation metrics using Python and Scikit-learn.

The notebook covers:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix
* Binary Classification
* Multi-class Classification

using:

* Logistic Regression
* Decision Tree Classifier

---

# 📂 Repository Structure

```text
├── Accuracy,precision,recall,F1_score.ipynb
├── heart.csv
├── iris.csv
└── README.md
```

---

# 🧠 Concepts Covered

## 🔹 Accuracy

Measures overall correctness of predictions.

Formula:

Accuracy = Correct Predictions / Total Predictions

---

## 🔹 Precision

Measures how many predicted positive values are actually positive.

Formula:

Precision = TP / (TP + FP)

---

## 🔹 Recall

Measures how many actual positive values were correctly predicted.

Formula:

Recall = TP / (TP + FN)

---

## 🔹 F1-Score

Harmonic mean of Precision and Recall.

Formula:

F1 Score = 2 × (Precision × Recall) / (Precision + Recall)

---

## 🔹 Confusion Matrix

Used to visualize classification performance.

Components:

* TP → True Positive
* TN → True Negative
* FP → False Positive
* FN → False Negative

---

# ⚙️ Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Jupyter Notebook

---

# 📊 Datasets Used

## 1️⃣ Heart Disease Dataset

Used for Binary Classification.

Features include:

* age
* sex
* cholesterol
* blood pressure
* heart rate
* etc.

---

## 2️⃣ Iris Dataset

Used for Multi-class Classification.

Classes:

* Iris-setosa
* Iris-versicolor
* Iris-virginica

---

# 🤖 Models Used

## Logistic Regression

Used for classification prediction tasks.

## Decision Tree Classifier

Used for comparison of classification performance.

---

# 📈 Results

## Binary Classification Results (Heart Dataset)

### Logistic Regression

* Accuracy = 0.839
* Precision = 0.786
* Recall = 0.92
* F1 Score = 0.848

### Decision Tree Classifier

* Accuracy = 0.980
* Precision = 0.962
* Recall = 1.0
* F1 Score = 0.980

---

## Multi-class Classification Results (Iris Dataset)

### Logistic Regression

* Accuracy = 1.0

### Decision Tree Classifier

* Accuracy = 1.0

---

# 📋 Classification Report

The project also demonstrates:

* Macro Average
* Weighted Average
* Per-class Precision
* Per-class Recall
* Per-class F1-score

using:

```python
classification_report()
```

---

# 🚀 How to Run

## Clone the Repository

```bash
git clone https://github.com/your-username/your-repository-name.git
```

---

## Install Required Libraries

```bash
pip install pandas numpy matplotlib scikit-learn
```

---

## Run Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
Accuracy,precision,recall,F1_score.ipynb
```

---

# 🎯 Learning Outcomes

Through this project, I learned:

* Importance of evaluation metrics
* Difference between Accuracy, Precision & Recall
* Binary vs Multi-class classification
* Confusion matrix interpretation
* Model performance comparison
* Classification report analysis

---

# 🔍 Key Observations

* Accuracy alone is not always sufficient
* Precision and Recall are important for imbalanced datasets
* F1-score balances Precision and Recall
* Decision Tree performed better on the heart dataset
* Multi-class evaluation requires averaging techniques

---

# 🔮 Future Improvements

* Add ROC-AUC Curve
* Implement Cross Validation
* Compare additional classification models
* Visualize confusion matrices using heatmaps
* Handle imbalanced datasets

---

# 🌟 Conclusion

This project strengthened my understanding of:

* Classification model evaluation
* Machine Learning metrics
* Performance comparison techniques
* Practical implementation of evaluation methods

---

⭐ Part of my Machine Learning Learning Journey

