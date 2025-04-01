# 🏈 Predicting Optimal NFL Play Type (Run or Pass)

## 📌 Project Overview

This project explores machine learning approaches to predict the **play type** (Run or Pass) in NFL games. By identifying patterns in play-calling decisions, this model aims to enhance strategic decision-making for teams, improve fan engagement, and provide valuable insights to coaches, players, and analysts alike.

---

## 📊 Problem Statement

The objective is to classify whether the next play in a football game will be a **run** or a **pass** based on contextual game variables. Accurate play-type prediction can offer a competitive edge in both defensive planning and in-game adjustments.

---

## 📁 Dataset and Preprocessing

- **Source**: NFL play-by-play data
- **Major cleaning steps**:
  - Dropped `points_scoredby_either_team` (96% missing)
  - Imputed `yards_gained` using median grouped by play type
  - Dropped records with missing values in `down` (0.36% rows)
  - Feature transformations and interaction variables (e.g., `time_pressure`, `two_minute_drill`, `down_distance_interaction`)
  - Normalized numerical features using `StandardScaler`
  - Applied one-hot encoding to categorical variables
  - Checked for multicollinearity using Variance Inflation Factor (VIF)

---

## 🧠 Machine Learning Models

The following models were trained and evaluated:

- K-Nearest Neighbors (KNN)
- Logistic Regression
- Support Vector Machine (SVM)
- Decision Tree
- Random Forest
- XGBoost

### 🏆 Best Model: Support Vector Machine (SVM)

| Metric      | Train (SVM) | Test (SVM) | Train (XGBoost) | Test (XGBoost) |
|-------------|-------------|------------|------------------|----------------|
| Accuracy    | 66.68%      | **66.91%** | 68.64%           | 65.45%         |
| Precision   | 72.98%      | **76.18%** | 69.06%           | 73.33%         |
| Recall      | 68.12%      | 65.52%     | 68.64%           | **66.94%**     |
| F1 Score    | **70.46%**  | **70.45%** | 68.78%           | 69.99%         |

SVM exhibited superior generalization and stability compared to XGBoost, with a better balance between precision and recall on unseen test data.

---

## 📌 Key Features Influencing Predictions

- `down` (0.195)
- `yards_gained` (0.256)
- `down_distance_interaction` (0.252)
- `two_minute_drill` (0.119)
- `point_differential` (0.126)
- `short_yardage` and `is_trailing` negatively correlated with pass plays

---

## 🎯 Real-World Applications

- Defensive coordinators can anticipate opponent strategies
- Coaches can adjust play-calling dynamically
- Analysts can use these insights for scouting and commentary
- Teams can simulate strategic situations in training

---

## 🛠️ Future Improvements

- Incorporate contextual features: weather, player matchups, team-specific tendencies
- Enable real-time predictions during live games
- Expand dataset to cover multiple seasons for deeper trend analysis

---

## 📂 Repository Contents

- `NFL_analysis.ipynb` — Complete EDA, feature engineering, model training & evaluation
- `NFL_Report.pdf` — Detailed project report & insights
- `README.md` — Project summary and instructions

---


   

