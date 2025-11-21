# Supervised Learning – Final Project
Finding employees satisfaction rating of PwC using ML - Hadiqa JAVAID, Manel RAHALI, Soumaya ATOUI

As part of the course Supervised Learning, this project requires building and iterating on a Machine Learning pipeline that solves a real business challenge, supported by a proper EDA, preprocessing, modelling, and experiment tracking workflow.

We tried three models CatBoost, RandomforestClassifier (Optional) and LightGBM(Optional) to perform the same results. All three models are uplaoded for reference. However, since catboost performed the best, we explained that more.

# 🧩 Business Use Case (BUC)
The company conducts a global annual employee engagement survey. Each employee provides:
- a satisfaction rating from 1 to 5,

- demographic information (country, position level, function),

- employment status (current or former),

- additional binary engagement indicators (recommender, commercial perspective, CEO approval).


Although the survey provides a numerical rating, the real business objective is not to predict the exact number (e.g., 3.8 or 4.2).
Predicting small variations of a satisfaction score does not help HR teams make meaningful decisions.
 
# ✔ What the business truly needs:
- Identify employees at risk of low satisfaction
  
- Understand which countries, roles or functions show higher risk

- Detect early warning signs based on engagement indicators

This aligns much better with a classification problem than a regression problem.

# 🎯 Why the ML target is NOT rating but at_risk
Rating (1–5) is highly skewed towards positive values: most employees give 4–5, and only a minority give 1–3.
Trying to predict these exact values would:
- produce meaningless outputs (e.g., “your predicted satisfaction is 4.1”)

- fail to answer the business question

- be sensitive to noise and unbalanced variations

- force us into a regression problem with no operational value

# ✔ To solve the real business problem, we transform rating into:
at_risk = 1 if rating <= 3 else 0
This makes the target:
- Binary categorical

- Meaningful

- Aligned with HR needs

- Suitable for classification algorithms

# ✔ Interpretation:
1 = at-risk employee (dissatisfied or potentially disengaged)
0 = not at risk (satisfied and stable)

👉 This transformation turns the project into a binary supervised classification task, which is far more aligned with real HR decision-making.
# 📊 Dataset
The dataset contains ~43,000 real survey responses, including:
Raw satisfaction rating (used only to create at_risk)

- Country (65 levels)

- Position level (7 levels)

- Function area (8 levels)

- Employee status (current or former)

- Binary engagement indicators (*_bin)

- Survey year

The dataset is real-world (not synthetic) and fully eligible for the project.

# 🧪 Data Science Methodology
✔ 1. EDA (Exploratory Data Analysis)
The EDA will:
- explore distributions

- examine missing values

- analyze satisfaction across countries, roles, functions

- inspect engagement indicators

- define and analyze the at_risk target

- identify class imbalance

- justify the features to be used in the ML model


# ✔ 2. Preprocessing
Performed in main.py, including:
- encoding categorical variables (OneHotEncoder)

- handling missing values

- splitting the data (train/test)

- creating a scikit-learn Pipeline

- preparing inputs for classification


# ✔ 3. Machine Learning Modelling
- Baseline (DummyClassifier)

- RandomForestClassifier

- Cross-validation

- Evaluation using ROC-AUC, F1, recall

- Feature importance

- Iterative experiment tracking (each experiment → commit)

We tried three models CatBoost, RandomforestClassifier (Optional) and LightGBM(Optional) to perform the same results. All three models are uplaoded for reference. However, since catboost performed the best, we explained that more. 

