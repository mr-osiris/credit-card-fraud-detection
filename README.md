# Credit Card Fraud Detection Using Machine Learning

This project uses machine learning to identify potentially fraudulent
credit card transactions. It compares three model configurations and
evaluates how well they detect fraud in an imbalanced dataset.

## Models Compared

-   **XGBoost with SMOTE:** Uses synthetic oversampling to help the
    model learn from fraudulent transactions.
-   **Class-Weighted XGBoost:** Gives more importance to fraudulent
    transactions during training.
-   **Class-Weighted Random Forest:** Uses class weights to account for
    the low number of fraud cases.

## Dataset

The project uses the [Credit Card Fraud Detection dataset on
Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud).

-   284,807 transactions
-   492 fraudulent transactions
-   `Class = 0`: Legitimate transaction
-   `Class = 1`: Fraudulent transaction

The dataset is highly imbalanced, with fraud representing about 0.17% of
transactions.

Download `creditcard.csv` from Kaggle and place it in the same folder as
the notebook.

## Technologies Used

-   Python
-   Jupyter Notebook
-   pandas and NumPy
-   scikit-learn
-   XGBoost
-   imbalanced-learn (SMOTE)
-   Matplotlib and Seaborn

## How to Run

1.  Download or clone this repository.

2.  Download `creditcard.csv` from the Kaggle link above.

3.  Place the CSV file beside `CreditCardFraudDetection.ipynb`.

4.  Install the required libraries:

    ``` bash
    pip install pandas numpy matplotlib seaborn scikit-learn xgboost imbalanced-learn jupyter
    ```

5.  Open and run `CreditCardFraudDetection.ipynb` in Jupyter Notebook or
    Google Colab.

**Note:** The notebook includes a synthetic-data fallback if the CSV is
missing. Results from synthetic data are not valid for measuring real
fraud detection performance. Use the Kaggle dataset for meaningful
results.

## Results

The notebook's recorded results are shown below.

  ----------------------------------------------------------------------------
  Model                 Precision         Recall       F1-score        ROC-AUC
  ---------------- -------------- -------------- -------------- --------------
  XGBoost + SMOTE          34.55%     **86.73%**         49.42%         97.60%

  Class-Weighted           75.93%         83.67%         79.61%         97.58%
  XGBoost                                                       

  Class-Weighted       **80.00%**         81.63%     **80.81%**     **98.27%**
  Random Forest                                                 
  ----------------------------------------------------------------------------

-   **Random Forest** achieved the highest precision, F1-score, and
    ROC-AUC in this experiment.
-   **XGBoost with SMOTE** achieved the highest recall, but its lower
    precision means it flags more legitimate transactions as fraud.
-   Accuracy is not enough to judge these models because fraudulent
    transactions are rare.

These results are from the existing notebook output and have not been
independently reproduced. They may change after improvements to the
experiment.

## Project Workflow

1.  Load and explore the transaction data.
2.  Prepare the features and target column.
3.  Split the data into training and test sets.
4.  Apply different class-imbalance strategies.
5.  Train the three model configurations.
6.  Compare their performance using evaluation metrics and plots.

## Limitations and Future Improvements

-   Fit the data scaler only on the training set to prevent data
    leakage.
-   Tune model settings and classification thresholds using validation
    data.
-   Test on later transactions using a time-based split.
-   Add Precision-Recall AUC and compare false-positive counts.
-   Consider deploying the selected model through an API or dashboard in
    a future version.

## Project Scope

This repository is a **machine learning model comparison project**. It
includes model training and evaluation in a notebook; it does not
currently provide a deployed API, frontend dashboard, or production
fraud monitoring system.

## Disclaimer

This project is for learning and portfolio purposes. It has not been
validated for real-world financial decisions.
