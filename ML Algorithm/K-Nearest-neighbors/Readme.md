# K-Nearest Neighbors (KNN) — Breast Cancer Classification

A **K-Nearest Neighbors classifier** built with scikit-learn to predict whether a breast tumor is **Malignant (M)** or **Benign (B)**, including hyperparameter tuning and interactive decision boundary visualization.

---

## Dataset

**`breast_cancer.csv`** — 569 samples, 30 numeric features extracted from digitized images of fine needle aspirate (FNA) of breast masses.

| Detail | Value |
|---|---|
| Total samples | 569 |
| Features used | 30 (dropped `id` and `Unnamed: 32`) |
| Target column | `diagnosis` — `M` (Malignant) / `B` (Benign) |
| Feature groups | Mean, Standard Error, and Worst values of: radius, texture, perimeter, area, smoothness, compactness, concavity, concave points, symmetry, fractal dimension |

---

## Workflow

### 1. Preprocessing
- Drop irrelevant columns (`id`, `Unnamed: 32`)
- Split into features `X` and target `y`
- 80/20 train-test split (`random_state=2`)
- Feature scaling with `StandardScaler` (fit on train, transform both)

### 2. Model Training
```python
from sklearn.neighbors import KNeighborsClassifier
knn = KNeighborsClassifier(n_neighbors=5)
knn.fit(X_train, y_train)
```

### 3. Hyperparameter Tuning — Finding Best K
Accuracy is evaluated for `k = 1` to `15` and plotted to find the optimal number of neighbors:

```python
scores = []
for i in range(1, 16):
    knn = KNeighborsClassifier(n_neighbors=i)
    knn.fit(X_train, y_train)
    scores.append(accuracy_score(y_test, knn.predict(X_test)))
plt.plot(range(1, 16), scores)
```

### 4. Interactive Decision Boundary Visualization
Uses `ipywidgets` to interactively explore how the decision boundary changes with different `k` values (1–20), plotted on the first 2 standardized features:

```python
interact(plot_decision_boundaries, n_neighbors=(1, 20), data=fixed(X), labels=fixed(y))
```

---

## Files

```
├── KNN.ipynb             # Main notebook — training, tuning, visualization
└── breast_cancer.csv     # Dataset (569 samples, 32 columns)
```

---

## Requirements

```bash
pip install numpy pandas scikit-learn matplotlib ipywidgets
```

Enable widgets in Jupyter (if not already):
```bash
jupyter nbextension enable --py widgetsnbextension
```

---

## Run

```bash
jupyter notebook KNN.ipynb
```

---

## Key Concepts Covered

- KNN algorithm — distance-based lazy learning
- Importance of feature scaling before KNN
- Train/test split and accuracy evaluation
- Hyperparameter tuning by iterating over `k` values
- Decision boundary visualization in 2D feature space
- Interactive widgets with `ipywidgets`
