# 🧠 Predicting Employee Attrition with Machine Learning

## 🎯 Project Overview

This project stems from a very real and recurring challenge in modern organizations: **understanding and preventing employee attrition**. While many companies rely on surveys or lagging indicators, our goal was to apply machine learning to proactively identify high-risk profiles and deliver actionable HR insights.

Rather than treating attrition as a one-size-fits-all problem, we wanted to uncover the **hidden drivers** behind employee decisions to leave — and to translate those patterns into **targeted retention strategies** by role, department, and demographic.

---

## 🧩 Project Goals

- Predict employee attrition using supervised machine learning models
- Understand **why** people leave, not just **who** is likely to leave
- Segment employees using unsupervised techniques to enhance interpretability
- Build a dashboard-ready output that HR teams can actually use

---

## 📊 Dataset & Preprocessing

This was a relatively small but **realistic and highly dimensional dataset** (35 variables, 1,470 employees), requiring careful attention to detail:

- **Outlier handling**: Preserved rather than removed, since edge cases are often where risk hides
- **Feature engineering**: Created 4 custom interaction features (e.g. `YearsAtCompany` × `JobLevel`) to better capture behavioral patterns
- **Encoding strategy**:
  - Ordinal variables encoded according to domain logic
  - Nominal variables one-hot encoded for model transparency
- **Feature scaling**:
  - Z-Score for normally distributed features
  - Min-Max scaling for skewed distributions
- **PCA**: Applied for certain models (e.g., Neural Network, Logistic Regression) to reduce noise and capture multidimensional signals

---

## 🧠 Supervised Learning Models

We tested a variety of models across different preprocessing pipelines:

| Model              | Notes                                                              |
|-------------------|--------------------------------------------------------------------|
| **Neural Network** | Best overall performer (PCA + Threshold tuning)                   |
| Logistic Regression | Great interpretability with good accuracy                         |
| SVM                | Balanced, consistent, but harder to explain                        |
| Random Forest      | Strong variable importance, good for HR feature analysis           |

Final choice: **Neural Network + PCA** — best precision/recall tradeoff and strongest early-warning capabilities.

---

## 🧪 Strategy Enhancements Tested

- **Class reweighting**: Worsened performance (overcompensation)
- **SMOTE (oversampling)**: Increased noise, reduced precision
- **Hyperparameter tuning**: Minor gains, original architecture (100, 50) held up best
- **Threshold tuning**: Most impactful — adjusting decision threshold significantly improved recall without flooding HR with false alarms

---

## 📈 Key Business Insights

- Attrition is driven by **multifactorial patterns**, not just job satisfaction
- **Sales** and **young managerial profiles** are highest-risk groups
- Even high-salary employees with good evaluations may still leave
- Created a **real-time dashboard view** that flags top 15 at-risk profiles (P > 85%)
- Provided department- and age-specific guidance for HR intervention

---

## 🔍 Unsupervised Learning

To enhance explainability and detect latent behavior patterns:

- **Clustering** was used on PCA components to segment employees by risk profiles
- Identified hidden segments not captured by standard HR metrics (e.g., high-income, low-satisfaction, mid-tenure cluster)

---

## 📁 Repository Structure

- `notebooks/` — Full pipeline: data preprocessing, feature engineering, model training, evaluation, and SHAP analysis *(FinalProject_AI_Enric.ipynb)*
- `data/` — Employee dataset 
- `business_case/` — Slide deck outlining the strategic and HR implications of the model *(Final Project Enric Aletà.pdf)*

---

## 👨‍💼 About Me

I'm Enric Aletà, a Business Analytics MSc student with a strong focus on bridging data science and real business impact. Projects like this one reflect the kind of work I want to keep doing — where machine learning moves from abstract models to tools that help people make better decisions.

Feel free to reach out via [LinkedIn](https://www.linkedin.com/in/enricaletacumellas/) if you'd like to exchange ideas on data-driven HR or predictive analytics.
