# data-science-journey
Social Network Data Cleaning (Python)

This project demonstrates how to clean and process social network data using pure Python. It works with a sample dataset of users, their friendships, and the pages they like.

Files in this Repository

data.json
Contains the raw dataset with two main sections:

users: each user’s id, name, list of friends, and liked pages.

pages: page id and name for different communities (Python, Data Science, AI/ML, Web Dev, etc.).

introduction.ipynb
A Jupyter Notebook with Python code to:

Load the data.json file

Clean and preprocess the dataset

Explore relationships between users and pages

Prepare the data for further analysis (e.g., recommendation systems, graph analysis)

Requirements

Python 3.x

Jupyter Notebook

No external libraries required (code uses only Python built-ins)

Usage

Clone this repository:

git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name


Open the notebook:

jupyter notebook introduction.ipynb


Run the cells to explore and clean the dataset.

Example Dataset

A snippet from data.json:

{
  "users": [
    {"id": 1, "name": "Amit", "friends": [2, 3], "liked_pages": [101]},
    {"id": 2, "name": "Priya", "friends": [1, 4], "liked_pages": [102]}
  ],
  "pages": [
    {"id": 101, "name": "Python Developers"},
    {"id": 102, "name": "Data Science Enthusiasts"}
  ]
}
