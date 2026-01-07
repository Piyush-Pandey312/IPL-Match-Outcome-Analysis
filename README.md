🏏 IPL Match Outcome & Player Impact Analysis (2008–2025)
📌 Project Overview

The Indian Premier League (IPL) is a fast-paced T20 cricket tournament where match outcomes can change rapidly based on key moments. Traditional statistics such as total runs or wickets often fail to capture the context and real impact of player performances.

This project builds an end-to-end analytics solution that:

Predicts win probability over-by-over

Quantifies player impact using probability shifts

Visualizes match momentum using an interactive Power BI dashboard

The project covers the full analytics lifecycle: data engineering → feature engineering → machine learning → BI visualization.

🎯 Problem Statement

How can we estimate the probability of winning an IPL match at any point in time and objectively measure player contributions beyond traditional statistics?

📂 Dataset

Source: Kaggle – IPL Dataset (2008–2025)

File: ipl.csv

Granularity: Ball-by-ball data

Key Columns Used:

Match context: match_id, innings, over, ball

Teams & players: batting_team, bowling_team, batter, bowler

Runs & wickets: runs_total, runs_target, player_out

Match result: match_won_by, season

🛠️ Tech Stack

Python (Pandas, NumPy)

Scikit-learn (Random Forest Classifier)

Jupyter Notebook

Power BI

DAX

CSV / Excel for data exchange

🔄 Project Workflow
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

🧠 Feature Engineering

The raw ball-by-ball data was transformed into match-state features:

Cumulative Runs

Cumulative Wickets

Overs Completed

Current Run Rate

Required Run Rate (for chasing innings)

Match Phase (Powerplay, Middle, Death)

Special care was taken to:

Handle missing and mixed data types

Prevent division-by-zero and infinite values

Avoid incorrect aggregation of cumulative metrics

🤖 Win Probability Model

Problem Type: Binary Classification (Win / Loss)

Model Used: Random Forest Classifier

Granularity: Over-level (aggregated from ball-level)

Target Variable: Whether the batting team eventually won the match

Output:
Win probability updated after every over.

Example:

After 15 overs, Team A has a 96% chance of winning.

⭐ Player Impact Score (Key Innovation)

Traditional stats do not capture when runs or wickets occur.
This project introduces a context-aware Player Impact Score.

Concept
Player Impact = Win Probability After Event − Win Probability Before Event

Why this matters:

Captures pressure situations

Accounts for match context

Works across batters and bowlers

Focuses on contribution toward winning

Player impacts are aggregated across matches to identify consistently influential players.

📊 Power BI Dashboard

An interactive dashboard was built using Power BI, featuring:

Key Visuals

📈 Win Probability vs Over (match momentum)

📋 Over-by-Over Match State Table

🧑‍🏏 Top 10 Players by Impact Score

📊 KPI Cards:

Current Runs

Current Wickets

Current Run Rate

Win Probability (%)

Slicers

Match ID

Batting Team

Inning (restricted to valid innings)

BI Best Practices Applied

Separation of fact and summary tables

No aggregation of cumulative metrics

Correct DAX context handling using “last over” logic

Clean, analytics-ready data loaded from Python

📁 Project Structure
IPL-Match-Outcome-Analysis/
│── data/
│   └── ipl.csv
│── notebooks/
│   └── IPL_Win_Probability_Model.ipynb
│── outputs/
│   ├── processed_match_state.csv
│   └── player_impact_scores.csv
│── powerbi/
│   └── IPL_Dashboard.pbix
│── README.md

📌 Key Insights

Early wickets significantly reduce win probability.

Required run rate spikes strongly influence match momentum.

Some players with moderate averages show very high impact in pressure situations.

Death-over performance has a disproportionate effect on match outcomes.

🚀 Future Enhancements

Live win probability API

Advanced ML models (XGBoost / LightGBM)

Season-wise and team-wise impact trends

Power BI Service deployment

Fantasy cricket analytics extension

🎓 What This Project Demonstrates

Real-world data cleaning and validation

Time-aware feature engineering

Machine learning for sports analytics

Advanced Power BI & DAX modeling

Business-oriented storytelling and visualization

👤 Author

Piyush Pandey
B.Tech (CSE) | Data Analytics & Machine Learning

This project is part of my data analytics portfolio.

📜 License

This project is for educational and portfolio purposes only.

✅ FINAL NOTE

This project was built with a focus on analytical correctness, clean modeling, and real interview expectations, rather than just visual appeal.
