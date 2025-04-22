# Email-Campaign-Optimization-Using-Machine-Learning

# 📧 Email Campaign Optimization Using Machine Learning

This project is a data-driven case study to help optimize email marketing strategies using Machine Learning models. The aim is to **identify which users are more likely to click on email links**, allowing for more targeted campaigns and improved click-through rates (CTR).

---

## 📂 Datasets Used

- `email_table.csv` – Base email data sent to users
- `email_opened_table.csv` – Which users opened the emails
- `link_clicked_table.csv` – Which users clicked on the email links

---

## 🔧 Key Tasks Performed

1. **Data Preparation**
   - Merged opened and clicked data with base email table
   - Handled categorical variables like `user_country`, `weekday`, `email_text`, `email_version`
   - One-hot encoding used for multi-class categorical features
   - Binned `user_past_purchases` into categorical ranges

2. **Exploratory Data Analysis (EDA)**
   - Visualized email performance metrics (opened, clicked)
   - Analyzed click behavior by past purchases
   - Investigated class imbalance

3. **Preprocessing**
   - Addressed class imbalance using **SMOTE** for the training set
   - Train-test split (60-40 ratio)

---

## 🤖 Models Used

### 1. Logistic Regression
- Implemented with `max_iter=1000`
- Achieved **Accuracy: 97%**
- ROC AUC Score: High
- Cross-validation **was not** applied here
- CTR uplift:
  - **Original CTR:** 2.12%
  - **Targeted CTR (Top 30% Prob):** 6.92%
  - 📈 **Improvement:** 4.80%

### 2. XGBoost Classifier
- SMOTE used to balance the dataset
- Achieved **Accuracy: 93%**
- **Cross-validation** (5-fold) was applied using AUC as the metric:
  - Cross-Validated AUC Scores: `[0.9497, 0.9539, 0.9558, 0.9541, 0.9543]`
  - **Average AUC:** 0.9535
- CTR uplift:
  - **Original CTR:** 2.12%
  - **Targeted CTR (Top 30% Prob):** 6.97%
  - 📈 **Improvement:** 4.85%

---

## 📊 Visualizations

- Bar charts for email performance
- Click rate by `user_past_purchases`
- Class distribution before SMOTE

---

## 📈 Business Insights

- Both models **significantly improved CTR** when targeting the top 30% of users predicted to click.
- Logistic Regression, despite being a simpler model, performed slightly better in accuracy, while XGBoost showed robust generalization in CV.
- Segmenting users based on past purchase behavior and personalizing emails increases engagement.

---

## 🛠 Tech Stack

- Python
- Pandas, NumPy
- Seaborn, Matplotlib
- Scikit-learn
- XGBoost
- imbalanced-learn (SMOTE)

---



---

## ✅ Notes

- Cross-validation was applied **only on XGBoost** using `cross_val_score`.
- Logistic Regression was evaluated using a simple train-test split.
  

---

