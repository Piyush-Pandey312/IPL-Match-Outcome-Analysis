# 🏏 **IPL Match Outcome & Player Impact Analysis (2008–2025)**  
## 📊 *Win Probability Modeling & Context-Aware Player Impact*

⭐ *An end-to-end sports analytics project combining Machine Learning and Power BI* ⭐

---

## 📌 **Project Overview**

The **Indian Premier League (IPL)** is a fast-paced T20 cricket tournament where match outcomes can change dramatically within a few overs.  
Traditional statistics such as total runs or wickets often fail to capture **context, pressure, and real impact**.

This project builds a **complete analytics pipeline** to:

✅ Predict **win probability over-by-over**  
✅ Quantify **player impact using probability shifts**  
✅ Visualize **match momentum** using an interactive **Power BI dashboard**

The project covers the **full analytics lifecycle**:

> **Data Engineering → Feature Engineering → Machine Learning → BI Visualization**

---

## 🎯 **Problem Statement**

> **How can we estimate the probability of winning an IPL match at any point in time and objectively measure player contributions beyond traditional statistics?**

---

## 📂 **Dataset**

- **Source:** Kaggle – IPL Dataset (2008–2025)  
- **File:** `ipl.csv`  
- **Granularity:** Ball-by-ball data  

### 🔑 Key Columns Used
- **Match Context:** `match_id`, `innings`, `over`, `ball`  
- **Teams & Players:** `batting_team`, `bowling_team`, `batter`, `bowler`  
- **Runs & Wickets:** `runs_total`, `runs_target`, `player_out`  
- **Match Result:** `match_won_by`, `season`

---

## 🛠️ **Tech Stack**

- **Python:** Pandas, NumPy  
- **Machine Learning:** Scikit-learn (Random Forest Classifier)  
- **Notebook:** Jupyter Notebook  
- **BI & Visualization:** Power BI  
- **Analytics Language:** DAX  
- **Data Format:** CSV / Excel  

---

## 🔄 **Project Workflow**

Raw IPL Data (ipl.csv)
↓
Data Cleaning & Validation
↓
Feature Engineering (Match State)
↓
Win Probability ML Model
↓
Player Impact Score Calculation
↓
Power BI Dashboard

---

## 🧠 **Feature Engineering**

Ball-by-ball data was transformed into **match-state features**, including:

- Cumulative Runs  
- Cumulative Wickets  
- Overs Completed  
- Current Run Rate  
- Required Run Rate (for chasing innings)  
- Match Phase (Powerplay, Middle, Death Overs)

### ⚠️ Key Data Handling Considerations
- Managed missing and mixed data types  
- Prevented division-by-zero and infinite values  
- Avoided incorrect aggregation of cumulative metrics  

---

## 🤖 **Win Probability Model**

- **Problem Type:** Binary Classification (Win / Loss)  
- **Model Used:** Random Forest Classifier  
- **Granularity:** Over-level (aggregated from ball-level)  
- **Target Variable:** Whether the batting team eventually won the match  

### 📈 Output
- Win probability updated **after every over**

**Example:**  
> After 15 overs, Team A has a **96% chance of winning**

---

## ⭐ **Player Impact Score (Key Innovation)**

Traditional statistics fail to capture **when** runs or wickets occur.  
This project introduces a **context-aware Player Impact Score**.

### 🔍 Concept

Player Impact = Win Probability After Event − Win Probability Before Event

### ✅ Why This Matters
- Captures pressure situations  
- Accounts for match context  
- Works for both batters and bowlers  
- Focuses on contribution toward **winning**, not just scoring  

Player impacts are aggregated across matches to identify **consistently influential players**.

---

## 📊 **Power BI Dashboard**

An interactive dashboard was developed using **Power BI**, featuring:

### 📈 Key Visuals
- Win Probability vs Over (Match Momentum)  
- Over-by-Over Match State Table  
- Top 10 Players by Impact Score  

### 📊 KPI Cards
- Current Runs  
- Current Wickets  
- Current Run Rate  
- Win Probability (%)  

### 🎛️ Slicers
- Match ID  
- Batting Team  
- Inning (restricted to valid innings only)

### ✅ BI Best Practices Applied
- Separation of fact and summary tables  
- No aggregation of cumulative metrics  
- Correct DAX context using “last over” logic  
- Analytics-ready data loaded from Python  

---

## 📁 **Project Structure**

IPL-Match-Outcome-Analysis/
│── data/
│ └── ipl.csv
│── notebooks/
│ └── IPL_Win_Probability_Model.ipynb
│── outputs/
│ ├── processed_match_state.csv
│ └── player_impact_scores.csv
│── powerbi/
│ └── IPL_Dashboard.pbix
│── README.md

---

## 📌 **Key Insights**

- Early wickets significantly reduce win probability  
- Required run rate spikes strongly influence match momentum  
- Some players with moderate averages show **very high impact under pressure**  
- Death-over performance has a disproportionate effect on match outcomes  

---

## 🚀 **Future Enhancements**

✨ Live win probability API  
✨ Advanced ML models (XGBoost / LightGBM)  
✨ Season-wise and team-wise impact trends  
✨ Power BI Service deployment  
✨ Fantasy cricket analytics extension  

---

## 🎓 **What This Project Demonstrates**

✔ Real-world data cleaning and validation  
✔ Time-aware feature engineering  
✔ Machine learning for sports analytics  
✔ Advanced Power BI & DAX modeling  
✔ Business-oriented storytelling and visualization  

---

## 👤 **Author**

**Piyush Pandey**  
B.Tech (CSE) | Data Analytics & Machine Learning  

This project is part of my **data analytics portfolio**.

---

## 📜 **License**

This project is for **educational and portfolio purposes only**.

---

## ✅ **Final Note**

This project was built with a strong focus on **analytical correctness, clean modeling, and real interview expectations**, rather than just visual appeal.

⭐ *If you found this project useful, don’t forget to star the repository!* ⭐
