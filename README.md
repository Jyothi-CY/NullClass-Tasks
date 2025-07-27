# Real-Time Google Play Store Data Analytics Dashboard

An end-to-end real-time data analytics project analyzing Google Play Store apps using Python, Pandas, Plotly, NLP, and GUI development tools. This project was built during my internship as a Data Analyst Intern and focuses on deriving interactive insights from app data, including user reviews, revenue, installs, and category trends.

---

## Project Overview

This project showcases real-time analytics on the Google Play Store dataset with the following goals:
- Clean, transform, and analyze structured and unstructured data.
- Apply Natural Language Processing (NLP) techniques to reviews.
- Build interactive visualizations using **Plotly** and **Tkinter**.
- Apply time-based logic to show different insights in a dashboard only during specified hours.

---

## Tools and Technologies Used

| Tool/Library      | Purpose                                 |
|-------------------|------------------------------------------|
| **Python**        | Core programming language                |
| **Pandas**        | Data cleaning and manipulation           |
| **NumPy**         | Numerical computations                   |
| **Plotly**        | Interactive and time-bound visualizations|
| **NLTK**          | NLP for review sentiment and keywords    |
| **Tkinter**       | GUI for desktop dashboard                |
| **Regex**         | Data normalization and pattern matching  |
| **Datetime + pytz** | Time-based conditional rendering        |
| **Googletrans**   | Translating categories in real-time      |

---

## Visualizations and Tasks Implemented

### Task 1: Word Cloud (5-Star Reviews in Health & Fitness)
- Reviews filtered by category: **Health & Fitness**
- Keywords extracted from only **5-star** ratings.
- Excluded stopwords and app names.
- Result: A vibrant word cloud showing user sentiment.

---

### Task 2: Dual-Axis Chart (Free vs Paid Apps)
- Categories: **Top 3 overall**
- Metrics: **Average Installs vs Revenue**
- Filters:
  - Installs > 10,000
  - Revenue > $10,000
  - Android version > 4.0
  - App size > 15MB
  - Content rating = Everyone
  - App name ≤ 30 characters
- Time Bound: Display only **between 1 PM – 2 PM IST**

---

### Task 3: Choropleth Map (Global Installs)
- Global install distribution using **country-wise view**
- Categories filtered:
  - Top 5 categories only
  - Excluded those starting with A, C, G, or S
- Highlighted categories with installs > 1 million
- Time Bound: Display only **between 6 PM – 8 PM IST**

---

### Task 4: Time Series Line Chart
- Install trends over time by app category
- Filters:
  - Reviews > 500
  - App name not starting with X, Y, Z
  - App name does not contain "S"
  - Categories starting with B, C, or E
- Category Translations:
  - Beauty → Hindi
  - Business → Tamil
  - Dating → German
- Highlights MoM growth > 20% with shaded area
- Time Bound: Display only **between 6 PM – 9 PM IST**

---

### Task 5: Bubble Chart (Rating vs Size)
- X-axis: App Size (MB)
- Y-axis: Average Rating
- Bubble Size: Number of Installs
- Filters:
  - Rating > 3.5
  - Reviews > 500
  - App name doesn’t contain “S”
  - Sentiment subjectivity > 0.5
  - Installs > 50,000
  - Categories included:
    - Game (highlighted pink)
    - Beauty (Hindi)
    - Business (Tamil)
    - Communication, Comics, Dating (German), Social, Entertainment, Event
- Time Bound: Display only **between 5 PM – 7 PM IST**

---

## Project Structure

NullClass-Tasks/
│
├── Cleaned Datasets/          
├── Datasets/                  
├── Graphs/                    
├── Task1/                      # Word Cloud 
├── Task2/                      # Dual-Axis Chart 
├── Task3/                      # Choropleth Map
├── Task4/                      # Time Series 
├── Task5/                      # Bubble Chart
│
├── .gitignore                  
├── GooglePlayStore.ipynb       
├── LICENSE                     
├── README.md                   
├── Tkinter_vs_HTML.ipynb       # Comparison of dashboards (Tkinter vs Web)



---

## Sentiment Analysis with NLP
- Used **NLTK** for tokenization and stopword removal.
- Analyzed sentiment polarity and subjectivity from user reviews.
- Applied filtering for **subjectivity > 0.5** in bubble chart analysis.
- Library: NLTK
- Techniques used:
       Tokenization
       Stopword removal
       Sentiment polarity & subjectivity filtering
       Sentiment analysis applied especially in bubble chart filtering.
---

## Time-Based Conditional Display

The dashboard includes logic to **show/hide charts depending on IST time** using:

```python
from datetime import datetime
import pytz

ist = pytz.timezone('Asia/Kolkata')
current_time = datetime.now(ist).time()
```
Each chart is conditionally loaded based on its time window.


---
## Clone the repo

# Step 1: Clone the repository
```
git clone https://github.com/Jyothi-CY/NullClass-Tasks.git
```
# Step 2: Navigate to the project directory
```
cd NullClass-Tasks
```
# Step 3: Open the project folder
```
cd "E:\Data Analyst Intern Tasks\Jupyter"
```

# Create and activate a virtual environment
```python -m venv venv
venv\Scripts\activate  # On Windows
```
# Step 4: Install dependencies
```
pip install -r requirements.txt
```
# Step 5: Run the main Jupyter Notebook
```
jupyter notebook GooglePlayStore.ipynb
```

---
## Key Outcomes
- Built a scalable, interactive analytics dashboard.
- Integrated sentiment, install, and revenue data with visual intelligence.
- Applied real-world constraints to simulate data-driven decision-making tools.

## License 
This project is licensed under the MIT License. See the LICENSE file for more information
