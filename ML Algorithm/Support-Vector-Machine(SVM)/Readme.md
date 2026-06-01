# ⚡ Support Vector Machines (SVM) — Complete Study Guide

> A hands-on collection of notebooks exploring **Support Vector Machines** — from linear classifiers and margin maximization to the powerful **Kernel Trick** for non-linear data.

---

## 📁 Repository Structure

```
📦 svm-study-guide/
 ┣ 📓 SVM_demo.ipynb
 ┗ 📓 SVM_kernel_trick.ipynb
```

---

## 📓 Notebooks

---

### 1. 🧲 `SVM_demo.ipynb` — SVM Fundamentals & Linear Classification

A thorough introduction to **SVM from the ground up** — starting with perfectly separable data and building up to soft-margin classification.

**What you'll learn:**
- 📐 What a **hyperplane**, **margin**, and **support vectors** are
- How to fit a linear SVM using `sklearn.svm.SVC`
- How to build a custom `plot_svc_decision_function` to visualize:
  - The **decision boundary** (solid line)
  - The **margin lines** (dashed lines)
  - The **support vectors** (circled points)
- Why adding more training points **doesn't move** the boundary — only support vectors matter!
- How the **regularization parameter `C`** controls the margin width

**Effect of `C` on the decision boundary:**

| `C` value | Effect |
|---|---|
| Very high (`100.0`) | Hard margin — fits training data tightly 🎯 |
| Very low (`0.01`) | Soft margin — wider margin, allows more errors 🌊 |

```python
from sklearn.svm import SVC

# Linear SVM
model = SVC(kernel='linear', C=1)
model.fit(X, y)

# Visualize
plt.scatter(X[:, 0], X[:, 1], c=y, cmap='winter')
plot_svc_decision_function(model)
plt.show()
```

**Datasets used:**
- 🟢 Perfectly linearly separable blobs (`make_blobs`, `cluster_std=0.60`)
- 🟡 Almost linearly separable blobs (`make_blobs`, `cluster_std=1.2`)

---

### 2. 🌀 `SVM_kernel_trick.ipynb` — The Kernel Trick for Non-Linear Data

Tackles the most powerful concept in SVM — the **Kernel Trick** — by working with circular data that a linear classifier simply cannot handle.

**What you'll learn:**
- Why a linear SVM **completely fails** (~50% accuracy) on circular data
- How to visualize a failed linear decision boundary
- The intuition behind the **kernel trick**: project data into a higher dimension where it *becomes* linearly separable
- 🧊 **3D visualization** of the RBF radial transformation — see the classes pull apart!
- Comparing three kernels side by side on the **same dataset**

**Dataset used:** `make_circles` — two concentric rings of points 🔵🔴

**Kernel comparison:**

| Kernel | How it works | Accuracy on circles |
|---|---|---|
| `linear` | Straight hyperplane | ❌ ~50% — Fails |
| `rbf` | Radial Basis Function — distance-based projection | ✅ ~100% — Perfect |
| `poly` (degree=2) | Polynomial surface | ✅ ~95%+ — Works |

**The "aha" moment 💡 — projecting 2D data into 3D:**

```python
# Radial transformation — lifts data into 3D
r = np.exp(-(X ** 2).sum(1))

ax = plt.subplot(projection='3d')
ax.scatter3D(X[:, 0], X[:, 1], r, c=y, cmap='bwr')
```

Once projected into 3D, the two circular classes sit at **different heights** and can be separated by a flat plane — that's the kernel trick in action!

```python
# RBF SVM — handles non-linear data perfectly
rbf_classifier = SVC(kernel="rbf")
rbf_classifier.fit(X_train, y_train)

# Polynomial SVM
poly_classifier = SVC(kernel="poly", degree=2)
poly_classifier.fit(X_train, y_train)
```

---

## 📈 Results Snapshot

| Model | Dataset | Accuracy |
|---|---|---|
| Linear SVM | Circular data | ❌ ~50% |
| RBF SVM | Circular data | ✅ ~100% |
| Polynomial SVM (degree=2) | Circular data | ✅ ~95%+ |

---

## 🧠 Concepts Covered

| Concept | Notebook |
|---|---|
| 📐 Hyperplane & Margins | `SVM_demo.ipynb` |
| 🔵 Support Vectors | `SVM_demo.ipynb` |
| 🎛️ C Regularization (Hard vs Soft Margin) | `SVM_demo.ipynb` |
| 🗺️ Decision Boundary Visualization | `SVM_demo.ipynb` |
| 🌀 Kernel Trick | `SVM_kernel_trick.ipynb` |
| 🔵 RBF Kernel | `SVM_kernel_trick.ipynb` |
| 📦 Polynomial Kernel | `SVM_kernel_trick.ipynb` |
| 🧊 3D Feature Projection | `SVM_kernel_trick.ipynb` |
| 📊 Accuracy Comparison across Kernels | `SVM_kernel_trick.ipynb` |

---

## 🛠️ Installation

```bash
git clone https://github.com/your-username/svm-study-guide.git
cd svm-study-guide
pip install -r requirements.txt
```

### 📦 Requirements

```txt
numpy
pandas
matplotlib
seaborn
scipy
scikit-learn
```

Or install directly:

```bash
pip install numpy pandas matplotlib seaborn scipy scikit-learn
```

---

## 🚀 Quick Start

```bash
# Launch Jupyter
jupyter notebook

# Start with SVM_demo.ipynb, then move to SVM_kernel_trick.ipynb
```

> 💡 **Recommended order:** `SVM_demo.ipynb` → `SVM_kernel_trick.ipynb`
> The demo builds the intuition; the kernel trick notebook blows your mind 🤯

---

## 🤝 Contributing

Contributions are welcome! Feel free to:
- 🐛 Open issues for bugs
- 💡 Suggest new notebooks (multi-class SVM, SVM regression, grid search tuning?)
- 🔧 Submit pull requests
---

## ⭐ Show Your Support

If this helped you understand SVMs, **drop a star** ⭐ — it keeps the repo alive!

---

*Made with ❤️ and a healthy obsession with ⚡ support vectors*
