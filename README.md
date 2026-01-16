# Mobile Plan Classification: Smart vs. Ultra 📱🤖

## 🎯 Business Objective
Megaline, a mobile carrier, wants to analyze customer behavior to recommend one of their two new plans: **Smart** or **Ultra**. The goal is to build a classification model with an accuracy of at least **0.75** to automate this recommendation process.

## 📊 Dataset Insights
The dataset contains behavior records from 3,214 users, including:
- `calls` & `minutes`: Number and duration of calls.
- `messages`: SMS sent.
- `mb_used`: Data consumption.
- `is_ultra`: Target variable (1 for Ultra, 0 for Smart).

## 🛠️ Machine Learning Pipeline
- **Preprocessing:** Data scaling using `StandardScaler` to normalize consumption features.
- **Model Selection:** I compared four different architectures:
  - Logistic Regression (Baseline)
  - Decision Tree
  - **Random Forest (Best Performer)**
  - Gradient Boosting
- **Optimization:** Hyperparameter tuning via `GridSearchCV` with 5-fold cross-validation.
- **Validation:** Rigorous split into Train, Validation, and Test sets (60/20/20).

## 🏆 Key Results
| Model | Test Accuracy |
| :--- | :--- |
| **Random Forest** | **0.821** |
| Gradient Boosting | 0.815 |
| Decision Tree | 0.802 |
| Logistic Regression | 0.740 |

**Winner:** The **Random Forest** model exceeded the target accuracy (0.75), achieving **82%** on unseen data.

## 🧪 Sanity Check
A permutation test was performed to ensure the model isn't picking up random noise. After shuffling labels, accuracy dropped to **0.58**, confirming the model's genuine predictive power based on user behavior patterns.

## 🚀 How to use
1. Clone the repo.
2. Install dependencies: `pip install -r requirements.txt`.
3. Run the notebook in `notebooks/`.
