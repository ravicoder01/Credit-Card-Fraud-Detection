# Credit-Card-Fraud-Detection
💳 Credit Card Fraud Detection using Machine Learning

An end-to-end Machine Learning project that detects fraudulent credit card transactions using Logistic Regression, with a strong focus on imbalanced data handling, precision–recall trade-offs, and real-world decision making.

This project is inspired by the core ideas from Andrew Ng’s Machine Learning course and demonstrates how ML theory is applied in practical, business-critical systems.

📌 Problem Statement

Credit card fraud is a rare but costly event.
The objective is to detect fraudulent transactions accurately while minimizing missed frauds, even when fraud cases account for less than 0.2% of all transactions.

## 🧠 Key Challenges

| Challenge | Description |
|----------|-------------|
| Extreme Class Imbalance | Fraud transactions represent ~0.17% of the dataset, making accuracy an unreliable metric |
| Metric Selection | Accuracy gives misleading results; precision and recall are more meaningful |
| False Negative Cost | Missing a fraud transaction leads to significant financial loss |
| Threshold Selection | Default threshold (0.5) performs poorly for fraud d

📊 Dataset

Source: Kaggle – Credit Card Fraud Detection (European cardholders)

Total Transactions: 284,807

Fraudulent Transactions: 492

Features:

V1–V28 → PCA-transformed features

Amount → Transaction amount

Class → Target label (0 = Normal, 1 = Fraud)

⚠️ Dataset is not included in this repository due to GitHub file size limits.

📥 How to get the dataset

Download the dataset from Kaggle

Place the file at:

data/creditcard.csv

## 🏗️ Project Pipeline

| Step | Description |
|------|------------|
| 1 | Data Loading & Exploration |
| 2 | Feature Scaling (`Amount`) |
| 3 | Train / Validation / Test Split (60/20/20) |
| 4 | Logistic Regression with Class Weights |
| 5 | Evaluation using Precision & Recall |
| 6 | Threshold Tuning via Precision–Recall Curve |
| 7 | Final Evaluation on Test Set |

## ⚙️ Technologies Used

| Category | Tools |
|---------|------|
| Language | Python |
| Libraries | NumPy, Pandas, Scikit-learn |
| Visualization | Matplotlib |
| Model | Logistic Regression |
| Evaluation | Precision, Recall, Confusion Matrix |

## 🧪 Data Preprocessing

| Task | Approach |
|------|----------|
| Missing Values | None present |
| Feature Scaling | Standardization of `Amount` |
| Feature Handling | PCA features + scaled amount |
| Data Split | Stratified sampling |

## 🤖 Model Details

| Aspect | Choice |
|-------|-------|
| Model | Logistic Regression |
| Loss Function | Log Loss |
| Regularization | L2 |
| Class Imbalance | `class_weight='balanced'` |
| Output | Probability of fraud |

## 📈 Evaluation Strategy

Due to extreme class imbalance, **accuracy was avoided**.

| Metric | Purpose |
|--------|--------|
| Precision | Measures false alarms |
| Recall | Measures missed fraud |
| Confusion Matrix | Error analysis |
| PR Curve | Threshold selection |

Default threshold (0.5) performed poorly

Threshold was tuned using the Precision–Recall Curve on the validation set

Threshold	Precision	Recall
0.50	High	Low
0.20	Medium	High
~0.02	Low	Very High

➡️ Threshold chosen to maximize recall while keeping precision acceptable.

✅ Final Test Results
Metric	Value
Precision	0.05
Recall	0.91
Interpretation

~91% of fraudulent transactions were detected

Some false positives are acceptable to minimize financial loss

🧠 Key Learnings

Accuracy is not suitable for imbalanced datasets

Precision–Recall trade-off depends on business cost

Threshold tuning is as important as model selection

ML systems must be evaluated in a real-world context

## 📂 Project Structure

```
credit-card-fraud-detection/
│
├── data/
│   └── creditcard.csv        # Dataset (not included due to size limit)
│
├── notebooks/
│   ├── 1_data_exploration.ipynb
│   ├── 2_preprocessing.ipynb
│   ├── 3_model_training.ipynb
│   ├── 4_threshold_tuning.ipynb
│   └── 5_final_evaluation.ipynb
│
├── README.md
├── requirements.txt
└── .gitignore
```


▶️ How to Run
pip install -r requirements.txt
jupyter notebook

🚀 Future Improvements

Neural Network model

Anomaly Detection approach

Ensemble methods

Feature importance analysis

Real-time fraud detection simulation

👤 Author

Ravi
B.Tech Student | Machine Learning Enthusiast
Focused on building real-world ML systems

⭐ Acknowledgment

Inspired by Andrew Ng’s Machine Learning course.
