# Machine Learning Practice – Perceptron Trick & Decision Boundary

This project demonstrates the implementation of a **Perceptron algorithm from scratch** and compares it with **Logistic Regression** using a synthetic dataset.
---
# Project Overview

In this notebook, I explored:

* Generating a classification dataset
* Visualizing data points
* Implementing the **Perceptron algorithm manually**
* Drawing the **decision boundary**
* Comparing results with **Logistic Regression**
* Observing how data separation affects model performance
---

# 1. Dataset Generation

```python
from sklearn.datasets import make_classification

X, y = make_classification(
    n_samples=100,
    n_features=2,
    n_informative=1,
    n_redundant=0,
    n_classes=2,
    random_state=41,
    class_sep=10
)
```

✔ Generated a 2D dataset for easy visualization
✔ Adjusted `class_sep` to control separability

---

# 2. Data Visualization

```python
plt.scatter(X[:,0], X[:,1], c=y, cmap='winter', s=100)
```

✔ Visualised two classes
✔ Clearly observed linear separability

---

# 3. Perceptron Implementation (From Scratch)

```python
def perceptron(X, y):
    X = np.insert(X, 0, 1, axis=1)
    weights = np.ones(X.shape[1])
    lr = 0.1

    for i in range(1000):
        j = np.random.randint(0, 100)
        y_hat = step(np.dot(X[j], weights))
        weights = weights + lr * (y[j] - y_hat) * X[j]

    return weights[0], weights[1:]
```

### Step Function

```python
def step(z):
    return 1 if z > 0 else 0
```

✔ Implemented Perceptron using gradient update logic
✔ Used random sampling for training

---

# 4. Decision Boundary (Perceptron)

```python
m = -(coef_[0] / coef_[1])
b = -(intercept_ / coef_[1])
```

✔ Converted weights into line equation
✔ Plotted decision boundary on graph

---

# 5. Logistic Regression (Comparison)

```python
from sklearn.linear_model import LogisticRegression

lor = LogisticRegression()
lor.fit(X, y)
```

✔ Used sklearn model for comparison
✔ Plotted its decision boundary alongside perceptron

---

# 6. Comparison

* **Red Line** → Perceptron
* **Black Line** → Logistic Regression

✔ Both models give similar results for linearly separable data
✔ Logistic Regression is more stable

---

# 7. Experiment: Changing Data Separation

```python
class_sep = 20
```

✔ Increased separation between classes
✔ Observed:

* Faster convergence
* Cleaner decision boundary

---

# Key Concepts Learned

* Linear Classification
* Perceptron Algorithm
* Decision Boundary Equation
* Gradient-based weight updates
* Difference between:

  * Perceptron
  * Logistic Regression

---

# Learning Outcome

After completing this project, I can:

* Implement Perceptron from scratch
* Visualize classification problems
* Plot decision boundaries
* Compare ML models
* Understand effect of data separability

---

# Tools & Libraries Used

* Python
* NumPy
* Matplotlib
* Scikit-learn

---

# Future Improvements

* Add non-linear datasets
* Implement kernel methods
* Compare with SVM
* Add accuracy evaluation metrics

---

⭐ This project is part of my **Machine Learning learning journey** and will be extended with more algorithms.

