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
📋 Project Overview
This project provides two core social network analysis functionalities:

Pages You Might Like - Recommends pages based on shared interests with friends

People You May Know - Suggests potential friends based on mutual connections

The system analyzes user relationships and page preferences to generate personalized recommendations.

🚀 Features
1. Page Recommendations (pagesyoumightlike.ipynb)
Algorithm: Collaborative filtering based on shared liked pages

Scoring: Pages are weighted by the number of shared interests with other users

Output: Ordered list of page IDs from most to least relevant

2. Friend Suggestions (peopleyoumayknow.ipynb)
Algorithm: Friends-of-friends with mutual connection counting

Scoring: Potential friends are ranked by number of mutual connections

Output: Ordered list of user IDs from most to least relevant

📊 Data Structure
Users Schema
json
{
  "id": "integer",
  "name": "string",
  "friends": ["array of user IDs"],
  "liked_pages": ["array of page IDs"]
}
Pages Schema
json
{
  "id": "integer", 
  "name": "string"
}
🛠️ Installation & Setup
Clone the repository

bash
git clone <your-repository-url>
cd <repository-directory>
Install dependencies

bash
pip install jupyterlab
Run Jupyter Notebook

bash
jupyter lab
📖 Usage
Page Recommendations
python
from pagesyoumightlike import find_pages_you_might_like

# Load data
data = read_data("massive.json")

# Get recommendations for user ID 1
recommendations = find_pages_you_might_like(1, data)
print(recommendations)  # Returns ordered list of page IDs
Friend Suggestions
python
from peopleyoumayknow import find_people_you_may_know

# Load data  
data = load_data("massive.json")

# Get suggestions for user ID 4
suggestions = find_people_you_may_know(4, data)
print(suggestions)  # Returns ordered list of user IDs
🧠 Algorithm Details
Page Recommendation Logic
For each user, identify their liked pages

Compare with other users' liked pages

For pages not already liked by the target user:

Add weight equal to number of shared pages with each other user

Sort pages by total weight in descending order

Friend Suggestion Logic
Identify direct friends of the target user

Find friends-of-friends (excluding direct friends)

Count mutual connections for each potential friend

Sort by mutual connection count in descending order

📈 Sample Data
The project includes massive.json containing:

30 users with complex friendship networks

27 pages covering various tech interests

Realistic social connections and preferences

🎯 Example Output
Page Recommendations for User 1:
text
[103, 105, 107, 104, 106, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127]
Friend Suggestions for User 4:
text
[2, 7, 5, 10, 12, 14, 11, 15]
🔧 Customization
Modify massive.json to add users, pages, or relationships

Adjust scoring algorithms in the respective notebook files

Extend functionality by adding new recommendation criteria

📝 Future Enhancements
Add user interface for easier interaction

Implement more sophisticated recommendation algorithms

Add visualization of social networks

Include page categories for better filtering

Add user similarity metrics beyond page likes
