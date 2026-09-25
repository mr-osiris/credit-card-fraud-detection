# 💳 Credit Card Fraud Detection Using Machine Learning

This project is focused on building an efficient fraud detection system using real-world anonymized credit card transaction data. The aim is to identify fraudulent transactions from legitimate ones using advanced machine learning models while handling extreme class imbalance.

# 📌 Objective

To detect credit card fraud accurately and efficiently using techniques like data preprocessing, class balancing (SMOTE), and modeling (XGBoost, Random Forest, etc.). The project focuses on minimizing false negatives (i.e., undetected frauds) while keeping false positives low enough to avoid inconveniencing real users.

---

# 📂 Dataset Overview

- Source: [Kaggle Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- Records: 284,807 transactions
- Features: 30 anonymized numerical features (`V1` to `V28`, `Time`, and `Amount`)
- Target: `Class` (0 = legit, 1 = fraud)
- Imbalance: Only ~0.17% of transactions are fraudulent

---

# 🧪 Approach & Methodology

### 🔄 Data Preprocessing:
- Handled extreme class imbalance using **SMOTE (Synthetic Minority Oversampling Technique)**
- Scaled `Amount` and `Time` using **StandardScaler**
- Ensured no data leakage from target column

# 📊 Exploratory Data Analysis:
- Visualized class distribution
- Correlation heatmaps to inspect feature relationships
- Checked for skewed features and distribution differences

# 🧠 Models Trained:
- **Random Forest Classifier**
- **XGBoost Classifier**
- Compared with and without SMOTE and scale_pos_weight

# 📈 Evaluation Metrics:
- **Confusion Matrix**
- **Precision, Recall, F1-score**
- **ROC-AUC Score**
- Focus on **Recall** to catch as many frauds as possible



## ✅ Key Results

| Model         | Precision | Recall | F1-score | ROC-AUC |
|---------------|-----------|--------|----------|---------|
| Random Forest | High      | Medium | Good     | ~0.98   |
| XGBoost (SMOTE) | High   | High   | Excellent| >0.99   |

- 📌 **XGBoost + SMOTE performed the best overall**
- 🚫 False negatives minimized — catching almost all frauds
- 🎯 ROC-AUC consistently > 0.99

---

# 💡 Conclusion & Recommendations

- **Deploy XGBoost with SMOTE** for real-time fraud detection
- Monitor model performance and retrain with recent data periodically
- Use threshold tuning depending on business risk tolerance
- Future work: try deep learning (autoencoders), real-time streaming, and more enriched feature sets

---

# 📁 Files in This Repo

- `CreditCardFraudDetection.ipynb` – complete code with analysis and models
- `creditcard.csv` – dataset used for training/testing
- `Results.pdf` – final summary of model evaluation
- `README.md` – this file 😉

---

# 🚀 Tools & Technologies Used

- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- Imbalanced-learn (SMOTE)
- XGBoost
- Google Colab

---

# 🙋‍♂️ About Me

I'm passionate about solving real-world problems using AI/ML, and this project is part of my learning journey into building high-impact machine learning systems.

Feel free to ⭐️ the repo or suggest improvements!


it suppose to detect credit card