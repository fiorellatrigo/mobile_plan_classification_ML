# Mobile Plan Classification: Smart vs. Ultra 📱🤖

## 🎯 Business Objective

Megaline, a mobile carrier, needs to analyze customer behavior to recommend one of their two primary plans: **Smart** or **Ultra**. The core objective of this project is to develop a classification model with a minimum accuracy of **0.75** to automate and personalize the plan recommendation process for existing subscribers.

## 📊 Dataset Insights

The analysis is based on behavior records from **3,214 users**, featuring:

* `calls` & `minutes`: Frequency and total duration of voice calls.
* `messages`: Number of SMS sent.
* `mb_used`: Monthly data consumption in megabytes.
* `is_ultra`: Target variable (1 for Ultra, 0 for Smart).

## 🛠️ Machine Learning Pipeline

* **Preprocessing:** Feature scaling using `StandardScaler` to normalize consumption metrics, ensuring model convergence.
* **Model Selection:** I evaluated four distinct architectures to find the optimal balance between bias and variance:
* **Logistic Regression** (Baseline)
* **Decision Tree**
* **Random Forest** (Winning Model)
* **Gradient Boosting**


* **Optimization:** Systematic hyperparameter tuning via `GridSearchCV` with 5-fold cross-validation.
* **Validation Strategy:** Data was partitioned into **Train (60%)**, **Validation (20%)**, and **Test (20%)** sets, using stratification to maintain class proportions.

## 🏆 Key Results

| Model | Test Accuracy |
| --- | --- |
| **Random Forest** | **0.821** |
| **Decision Tree** | **0.804** |
| **Gradient Boosting** | **0.796** |
| **Logistic Regression** | **0.740** |

**Winner:** The **Random Forest** model emerged as the most robust solution, significantly exceeding the business target (0.75) by achieving an **82.11% accuracy** on unseen data.

## 🧪 Sanity Check

To ensure the model captured genuine behavioral patterns rather than noise, a **permutation test** was performed. After shuffling the feature indices, the accuracy dropped to **0.58** (close to random chance). This confirms the model's high predictive power and its ability to generalize to new subscribers.

## 🚀 How to use

1. Clone the repository.
2. Install dependencies: `pip install -r requirements.txt`.
3. Open and run the notebook: `Project_Sprint_10.ipynb`.

---

**Analysis by Fiorella Trigo M.**
**Part 2 of the Megaline Optimization Series**