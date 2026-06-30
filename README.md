# Mobile Plan Classification: Smart vs. Ultra

## 1. The Problem
Megaline, a mobile carrier, needs to transition from manual or generalized upselling to an automated, data-driven approach. The company requires a robust system to analyze existing customer behavior and accurately recommend one of their two primary plans (Smart or Ultra) to personalize the user experience and optimize plan allocation.

## 2. Objective
The core objective of this project is to develop a classification model with a minimum accuracy threshold of 0.75 to automate and personalize plan recommendations for existing Megaline subscribers based on their usage behavior.

## 3. Methodology
* **Data & Target:** Analyzed behavior records from 3,214 users, featuring voice calls (frequency and total minutes), SMS sent, and monthly data consumption (`mb_used`). The target variable is `is_ultra` (1 for Ultra, 0 for Smart).
* **Preprocessing:** Applied feature scaling using `StandardScaler` to normalize consumption metrics, ensuring model convergence.
* **Validation Strategy:** Data was partitioned into Train (60%), Validation (20%), and Test (20%) sets, utilizing stratification to maintain strict class proportions.
* **Modeling & Optimization:** Evaluated four distinct architectures (Logistic Regression as the baseline, Decision Tree, Random Forest, and Gradient Boosting) to find the optimal balance between bias and variance. Implemented systematic hyperparameter tuning via `GridSearchCV` with 5-fold cross-validation.

## 4. Findings
### Model Performance

| Model | Test Accuracy |
| --- | --- |
| **Random Forest** | **0.821** |
| **Decision Tree** | **0.804** |
| **Gradient Boosting** | **0.796** |
| **Logistic Regression** | **0.740** |

* **Target Achievement:** The Random Forest model emerged as the winning architecture, significantly exceeding the business target (0.75) by achieving an **82.11% accuracy** on unseen data.
* **Sanity Check:** To ensure the model captured genuine behavioral patterns rather than noise, a permutation test was performed. After shuffling the feature indices, the accuracy dropped to **0.58** (close to random chance). This statistical confirmation supports the model's high predictive power and its ability to generalize to new subscribers.

## 5. Recommendations
* **Automated Allocation:** Deploy the optimized Random Forest model into Megaline's production environment to proactively automate subscriber plan upgrades based on their daily data and call limits.
* **Data-Driven Marketing:** Utilize the classification engine to filter and target existing Smart plan users whose behavioral metrics align with the Ultra profile, maximizing the ROI of promotional campaigns.

## 6. Technologies
* **Language:** Python
* **Machine Learning Framework:** Scikit-Learn
* **Core Techniques:** Classification Architectures, GridSearchCV, Feature Scaling, Stratified Splitting, Permutation Testing

---

## Project Structure
```text
├── data/                  # Local directory for raw dataset
├── notebooks/             # Jupyter Notebooks containing EDA and Modeling
├── README.md              # Project executive summary and documentation
└── requirements.txt       # Project dependencies

```

---
## Installation & Usage

1. Clone the repository.
2. Install dependencies: `pip install -r requirements.txt`
3. Open and run the notebook: `Project_Sprint_10.ipynb`

---
*Analysis by Fiorella Trigo M.*  
*Part 2 of the Megaline Optimization Series*
