# 🌳 Decision Tree Machine Learning — Complete Study Guide

> A hands-on collection of notebooks exploring **Decision Trees** for classification, regression, visualization, and model tuning using real-world datasets.
---

## 📁 Repository Structure

```
📦 decision-tree-ml/
 ┣ 📓 dtreeviz_demo.ipynb
 ┣ 📓 Overfitting_and_underfitting_in_decision_tree.ipynb
 ┣ 📓 regression_tree_example.ipynb
 ┣ 📊 Social_Network_Ads.csv
 ┗ 🚗 cars.csv
```

---

## 📊 Datasets

### 👥 Social Network Ads (`Social_Network_Ads.csv`)
A marketing dataset used for **binary classification** — predicting whether a user purchased a product based on their profile.

| Column | Type | Description |
|---|---|---|
| `User ID` | int | Unique identifier |
| `Gender` | str | Male / Female |
| `Age` | int | User's age |
| `EstimatedSalary` | int | Annual salary estimate |
| `Purchased` | int | Target — 0 (No) / 1 (Yes) |

- **Rows:** 400 &nbsp;|&nbsp; **Columns:** 5
- **Task:** Binary Classification

---

### 🚗 Cars (`cars.csv`)
A classic automotive dataset used for **regression** — predicting fuel efficiency (mpg) from car specs.

| Column | Type | Description |
|---|---|---|
| `mpg` | float | Miles per gallon (target) |
| `cylinders` | int | Number of cylinders |
| `displacement` | float | Engine displacement |
| `horsepower` | float | Engine horsepower |
| `weight` | int | Car weight |
| `acceleration` | float | 0–60 mph time |
| `model-year` | int | Year of manufacture |

- **Rows:** 398 &nbsp;|&nbsp; **Columns:** 7
- **Task:** Regression

---

## 📓 Notebooks

### 1. 🎨 `dtreeviz_demo.ipynb` — Beautiful Tree Visualization

Explore how to render **stunning, interpretable decision tree diagrams** using the `dtreeviz` library.

**What you'll learn:**
- 🌸 Classification tree on the **Iris dataset** (setosa / versicolor / virginica)
- 🏠 Regression tree on the **California Housing dataset**
- 🔄 Horizontal tree layout for better readability
- How to annotate trees with feature names and class names

**Key libraries:** `dtreeviz`, `sklearn`, `graphviz`

```python
import dtreeviz

viz = dtreeviz.model(clf, X_train, y_train,
                     feature_names=iris.feature_names,
                     class_names=["setosa", "versicolor", "virginica"])
viz.view()
```

---

### 2. 📉 `Overfitting_and_underfitting_in_decision_tree.ipynb` — Bias-Variance Tradeoff

A visual deep-dive into one of the most important concepts in ML — **overfitting and underfitting** — using the Social Network Ads dataset.

**What you'll learn:**
- How `max_depth` controls model complexity
- Visualizing decision boundaries with `meshgrid` contour plots
- The effect of `max_depth = None` (full tree → overfitting)
- Step-by-step comparison: `max_depth = 1, 2, 3, 4, None`

**Core idea:**

| `max_depth` | Model Behavior |
|---|---|
| 1 | Underfitting — too simple |
| 2–3 | Balanced — good generalization ✅ |
| 4+ | Starts overfitting |
| `None` | Severely overfits 🚨 |

```python
def analyzer(max_depth):
    clf = DecisionTreeClassifier(max_depth=max_depth)
    clf.fit(X, y)
    # Plot decision boundary with contourf
    ...

analyzer(max_depth=3)  # Try different depths!
```

---

### 3. 🔢 `regression_tree_example.ipynb` — Regression Tree + Hyperparameter Tuning

End-to-end regression pipeline using the **California Housing dataset**, with grid search to find the best model.

**What you'll learn:**
- Building a `DecisionTreeRegressor` from scratch
- Evaluating with **R² score**
- `GridSearchCV` hyperparameter tuning
- **Feature importance** ranking

**Hyperparameters tuned:**

| Parameter | Values Explored |
|---|---|
| `max_depth` | 2, 4, 8, 10, None |
| `criterion` | squared_error, absolute_error |
| `max_features` | 0.25, 0.5, 1.0 |
| `min_samples_split` | 0.25, 0.5, 1.0 |

**Top features by importance (example output):**
```
MedInc        0.58
AveOccup      0.14
Latitude      0.10
Longitude     0.09
...
```

---

## 🛠️ Installation

```bash
git clone https://github.com/your-username/decision-tree-ml.git
cd decision-tree-ml
pip install -r requirements.txt
```

### 📦 Requirements

```txt
numpy
pandas
matplotlib
scikit-learn
dtreeviz
graphviz
pandas-datareader
```

Or install directly:

```bash
pip install numpy pandas matplotlib scikit-learn dtreeviz graphviz pandas-datareader
```

> ⚠️ **Note:** `dtreeviz` requires `graphviz` to be installed on your system as well.
> - **Ubuntu/Debian:** `sudo apt-get install graphviz`
> - **macOS:** `brew install graphviz`
> - **Windows:** [Download from graphviz.org](https://graphviz.org/download/)

---

## 🚀 Quick Start

```bash
# Launch Jupyter
jupyter notebook

# Open any notebook and run all cells!
```

---

## 🧠 Concepts Covered

| Concept | Notebook |
|---|---|
| 🎨 Tree visualization | `dtreeviz_demo.ipynb` |
| 📉 Overfitting | `Overfitting_and_underfitting...` |
| 📈 Underfitting | `Overfitting_and_underfitting...` |
| 🔢 Regression Trees | `regression_tree_example.ipynb` |
| ⚙️ Hyperparameter Tuning | `regression_tree_example.ipynb` |
| 🏆 Feature Importance | `regression_tree_example.ipynb` |
| 🗺️ Decision Boundaries | `Overfitting_and_underfitting...` |

---

## 📈 Results Snapshot

- ✅ **Classification accuracy** on Social Network Ads: ~85–90% at optimal depth
- ✅ **R² score** on California Housing (base model, `max_depth=5`): ~0.72
- ✅ **R² score** after GridSearchCV tuning: improved further with optimal params

---

## 🤝 Contributing

Contributions are welcome! Feel free to:
- 🐛 Open issues for bugs
- 💡 Suggest new notebook ideas
- 🔧 Submit pull requests

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## ⭐ Show Your Support

If you found this helpful, **give it a star** ⭐ — it means a lot!
