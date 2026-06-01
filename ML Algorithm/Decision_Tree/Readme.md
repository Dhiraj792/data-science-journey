# Decision Tree Visualization and Analysis with DTreeViz

## 📌 Project Overview

This repository demonstrates various concepts of Decision Trees using Python, Scikit-Learn, and DTreeViz. The project includes:

* Decision Tree Classification
* Decision Tree Regression
* Decision Tree Visualization using DTreeViz
* Overfitting and Underfitting Analysis
* Model Evaluation and Interpretation

The notebooks provide practical examples using popular datasets such as the Iris Dataset, California Housing Dataset, and Social Network Ads Dataset.

---

## 📂 Repository Structure

```text
├── dtreeviz_demo.ipynb
├── regression_tree_example.ipynb
├── Overfitting and underfitting in decision tree.ipynb
├── cars.csv
├── Social_Network_Ads.csv
└── README.md
```

---

## 📖 Notebooks Description

### 1️⃣ DTreeViz Demo (`dtreeviz_demo.ipynb`)

This notebook demonstrates:

* Training a Decision Tree Classifier
* Visualizing decision trees using DTreeViz
* Working with the Iris Dataset
* Tree structure interpretation
* Feature importance visualization
* Understanding decision boundaries

**Libraries Used:**

* Scikit-Learn
* DTreeViz
* Graphviz
* Matplotlib

---

### 2️⃣ Regression Tree Example (`regression_tree_example.ipynb`)

This notebook covers:

* Decision Tree Regression
* California Housing Dataset
* Data preprocessing
* Train-test split
* Model training and prediction
* Performance evaluation using:

  * R² Score
  * Mean Absolute Error
  * Mean Squared Error

**Objective:** Learn how Decision Trees can be used for regression problems.

---

### 3️⃣ Overfitting and Underfitting in Decision Trees (`Overfitting and underfitting in decision tree.ipynb`)

This notebook demonstrates:

* Effect of varying `max_depth`
* Underfitting scenarios
* Overfitting scenarios
* Decision boundary visualization
* Model complexity analysis

Dataset used:

* Social Network Ads Dataset

**Key Learning:**
Understanding how tree depth affects model generalization and performance.

---

## 🛠️ Installation

Clone the repository:

```bash
git clone https://github.com/your-username/decision-tree-dtreeviz.git
cd decision-tree-dtreeviz
```

Install required packages:

```bash
pip install pandas numpy matplotlib scikit-learn dtreeviz graphviz pandas-datareader
```

---

## ⚙️ Graphviz Setup

DTreeViz requires Graphviz to be installed separately.

### Windows

1. Download Graphviz from:
   https://graphviz.org/download/

2. Install Graphviz.

3. Add Graphviz `bin` folder to Environment Variables:

```text
C:\Program Files\Graphviz\bin
```

4. Verify installation:

```bash
dot -V
```

---

## 🚀 How to Run

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open any notebook and execute the cells sequentially.

---

## 📊 Technologies Used

* Python
* Jupyter Notebook
* Scikit-Learn
* DTreeViz
* Graphviz
* Pandas
* NumPy
* Matplotlib

---

## 🎯 Learning Outcomes

After completing these notebooks, you will understand:

* Decision Tree Classification
* Decision Tree Regression
* Tree Visualization Techniques
* Feature Importance Analysis
* Overfitting vs Underfitting
* Model Interpretation using DTreeViz

---

## 🤝 Contributing

Contributions, improvements, and suggestions are welcome.

1. Fork the repository
2. Create a feature branch
3. Commit changes
4. Open a Pull Request

---

## 📜 License

This project is intended for educational and learning purposes.

---

## ⭐ Support

If you found this project useful, consider giving it a star on GitHub.

