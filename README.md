# 📊 Data Science Journey 🚀

## Social Network Data Cleaning & Recommendation System (Python)

This project demonstrates how to **clean, process, and analyze social network data using Python**.
It also implements basic **recommendation systems** for suggesting pages and friends.
---
# 📌 Project Overview

This project works with a social network dataset containing:

* Users and their friendships
* Pages liked by users

It performs:

* Data cleaning and preprocessing
* Relationship analysis
* Recommendation generation

---
# 📂 Repository Structure

```
data-science-journey/
│── data.json
│── massive.json
│── introduction.ipynb
│── pagesyoumightlike.ipynb
│── peopleyoumayknow.ipynb
│── README.md
```

---

# 📁 Files Description

### 🔹 data.json

Contains raw dataset:

* Users (id, name, friends, liked pages)
* Pages (id, name)

---

### 🔹 introduction.ipynb

* Loads dataset
* Cleans and preprocesses data
* Explores relationships
* Prepares data for analysis

---

### 🔹 pagesyoumightlike.ipynb

Implements **Page Recommendation System**

* Uses collaborative filtering
* Suggests pages based on shared interests

---

### 🔹 peopleyoumayknow.ipynb

Implements **Friend Recommendation System**

* Uses mutual connections
* Suggests potential friends

---

# 📊 Data Structure

## Users

```json
{
  "id": 1,
  "name": "Amit",
  "friends": [2, 3],
  "liked_pages": [101]
}
```

## Pages

```json
{
  "id": 101,
  "name": "Python Developers"
}
```

---

# 🚀 Features

## 1️⃣ Pages You Might Like

* Based on **common interests**
* Uses collaborative filtering
* Ranks pages by relevance

✔ Output: Ordered list of page IDs

---

## 2️⃣ People You May Know

* Based on **mutual friends**
* Uses friends-of-friends logic
* Ranks users by number of shared connections

✔ Output: Ordered list of user IDs

---

# 🧠 Algorithms Used

## Page Recommendation

* Compare user liked pages with others
* Assign weights based on similarity
* Recommend unseen pages

---

## Friend Recommendation

* Find friends-of-friends
* Count mutual connections
* Rank users accordingly

---

# 🛠️ Requirements

* Python 3.x
* Jupyter Notebook

✔ No external libraries required

---

# ⚙️ Installation & Setup

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
pip install jupyterlab
jupyter lab
```

---

# 📖 Usage

## Page Recommendation

```python
from pagesyoumightlike import find_pages_you_might_like

data = read_data("massive.json")
recommendations = find_pages_you_might_like(1, data)
print(recommendations)
```

---

## Friend Suggestions

```python
from peopleyoumayknow import find_people_you_may_know

data = load_data("massive.json")
suggestions = find_people_you_may_know(4, data)
print(suggestions)
```

---

# 📈 Sample Output

### Page Recommendations (User 1)

```
[103, 105, 107, 104, 106, ...]
```

### Friend Suggestions (User 4)

```
[2, 7, 5, 10, 12, ...]
```

---

# 🎯 Learning Outcomes

Through this project, I learned:

* Data cleaning using Python
* Working with JSON datasets
* Graph-based relationship analysis
* Building recommendation systems
* Implementing logic without external libraries

---

# 🔧 Future Improvements

* Add UI (Web/App)
* Improve recommendation algorithms
* Add visualization (network graphs)
* Use ML-based recommendation models
* Add user similarity metrics

---

# 🌟 Conclusion

This project demonstrates how raw social network data can be transformed into meaningful insights and recommendations using **core Python logic**.

---

⭐ Part of my **Data Science learning journey**
