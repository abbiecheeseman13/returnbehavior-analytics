# Behavioral Return Prediction  
Predicting user return likelihood using behavioral, engagement, and session-level features

This project analyzes a simulated Duolingo-style dataset to understand which user behaviors most strongly predict whether someone will return to the app. The goal is to replicate the kind of retention analysis performed in real product and growth analytics teams, where the focus is on identifying at-risk users and surfacing the behavioral patterns behind long-term engagement.

The notebook includes exploratory data analysis, feature engineering, multiple machine learning models, and explainability techniques.

---

## 1. Project Objective

The goal of this project is to:

1. **Understand engagement patterns** among app users  
2. **Predict whether a user is likely to return** using behavioral and session data  
3. **Identify the strongest behavioral drivers** of retention  
4. **Translate those findings into actionable product insights** for a real-world scenario  

This type of analysis mirrors common workflows at companies like Duolingo, Babbel, Quizlet, or any product that depends on daily or weekly active usage.

---

## 2. Dataset Description

The dataset used in this project is:  
`duolingo_behavior_simulated_dataset.csv`  
*(fully synthetic and generated for educational/portfolio purposes)*

Key columns in the dataset:

- `user_id`  
- `total_sessions`  
- `total_days_active`  
- `avg_session_length`  
- `streak_length`  
- `xp_earned`  
- `lessons_completed`  
- `hearts_remaining`  
- `ads_watched`  
- `subscription_status` (free vs paid)
- `country`
- `time_of_day_usage`
- **Target: `returned`** (1 = the user returned within the retention window, 0 = churned)

### Additional engineered features in the notebook:

- Session-normalization metrics (xp per session, lessons per session)  
- Recent activity indicators  
- Streak-related ratios  
- Binned categorical features for modeling  
- Scaled numerical features for models that require them  

These help uncover behavioral patterns that drive retention.

---

## 3. Workflow Overview

The notebook, `behavior-return-prediction-analysis.ipynb`, contains:

### **1) Exploratory Data Analysis (EDA)**
- Summary statistics  
- Distribution plots of engagement metrics  
- Return vs non-return comparisons  
- Correlation maps  
- Behavioral differences between paid and free users  

### **2) Feature Engineering**
- Session-based ratios  
- Recency indicators  
- Streak and XP transformations  
- Encoding of categorical variables  
- Scaling of numeric fields for certain models  

### **3) Modeling**
The project trains and evaluates:

- **Logistic Regression**
- **Random Forest**
- **XGBoost** (if installed)

Each model outputs:

- Accuracy  
- Precision, Recall, F1 Score  
- ROC-AUC  

A comparison table summarizes the winners.

### **4) Explainability**
To understand *why* predictions are being made, the notebook includes:

- Top coefficients (Logistic Regression)  
- Feature importances (Random Forest / XGBoost)  
- Optional SHAP values for deeper model interpretability  

This is the most important part from a product perspective, since it explains which behaviors matter.

### **5) Product & Growth Insights**
The notebook closes with a plain-English summary of:

- High-value behaviors associated with returns  
- Risk indicators for churn  
- What product or lifecycle teams could do with these insights  
- Opportunities to test interventions  

---

## 4. Key Findings (Example Summary)

Your exact model output will vary, but in this simulated dataset:

- **Streak length** is the strongest predictor of return  
- **Total sessions** and **days active** strongly correlate with retention  
- **XP earned per session** indicates deeper engagement  
- **Paid subscribers** have significantly higher return rates  
- **Users with very short session lengths** are at higher risk  
- Engagement during **consistent times of day** predicts reliability  
- Low-streak, low-XP, and low-frequency users are the highest churn risk
