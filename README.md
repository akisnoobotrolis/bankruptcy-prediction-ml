# Bankruptcy Prediction ML

This project is a comparative study of Machine Learning models designed to predict corporate bankruptcy based on financial indicators. The primary focus is on handling **imbalanced datasets** and optimizing models to meet specific performance constraints (Recall & Specificity).

## 📌 Project Overview

The goal is to classify companies as **Healthy** or **Bankrupt** using a dataset of financial ratios. Since bankruptcy is a rare event, the dataset is highly imbalanced. This project explores techniques to mitigate this issue and build reliable predictive models.

### Key Objectives
*   Data Preprocessing & Normalization.
*   Handling Class Imbalance via **Downsampling** and **Class Weights**.
*   Training multiple classifiers (SVM, Logistic Regression, KNN, MLP, etc.).
*   Evaluating models based on strict constraints:
    *   **Recall (Bankrupt) ≥ 62%** (Minimizing False Negatives is crucial).
    *   **Specificity (Healthy) ≥ 70%**.

## 📂 Dataset

The dataset (`Dataset2Use_Assignment.xlsx`) consists of:
*   **Features**: 11 Financial Indicators (Performance & Activity ratios).
*   **Target**: Status (1 = Healthy, 2 = Bankrupt).
*   **Preprocessing**: The target was re-mapped to binary (0 = Healthy, 1 = Bankrupt) and features were scaled using `StandardScaler`.

## ⚙️ Methodology

1.  **Data Splitting**: Stratified Train/Test split (75/25).
2.  **Class Balancing**:
    *   **Downsampling**: Reduced the majority class (Healthy) in the training set to achieve a 3:1 ratio.
    *   **Weighted Loss Functions**: Applied custom class weights (e.g., 1:2.2, 1:3) to penalize misclassification of bankrupt companies more heavily.
3.  **Models Evaluated**:
    *   Logistic Regression
    *   Support Vector Machines (SVM) - *RBF Kernel*
    *   K-Nearest Neighbors (KNN)
    *   Linear Discriminant Analysis (LDA)
    *   Naïve Bayes (GaussianNB)
    *   Neural Networks (MLP Classifier)

## 📊 Results

The models were evaluated on a test set. While standard accuracy was high across the board, it was misleading due to the imbalance.

*   **Best Performing Model**: `SVM (RBF) with Class Weights (1:2.2)`
*   **Performance**:
    *   **Accuracy**: ~83.4%
    *   **Recall (Bankrupt)**: ~66.1% (Met constraint ≥ 62%)
    *   **Specificity (Healthy)**: ~83.8% (Met constraint ≥ 70%)

Detailed results are exported to `output/classification_results.xlsx`.

## 🚀 Usage

1.  Clone the repository.
2.  Ensure `Dataset2Use_Assignment.xlsx` is in the project root.
3.  Run the Jupyter Notebook `askisi.ipynb`.
