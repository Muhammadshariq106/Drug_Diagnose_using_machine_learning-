Drug Classification Using Machine Learning
Overview

This project builds and evaluates multiple machine learning classification models to predict the appropriate drug for a patient based on medical attributes such as:

Age
Sex
Blood Pressure (BP)
Cholesterol Level
Sodium-to-Potassium Ratio (Na_to_K)

The project includes data exploration, preprocessing, model training, evaluation, comparison, and prediction on new patient records.

Dataset

The project uses the Drug200 dataset containing patient information and the corresponding prescribed drug.

Features
Feature	Description
Age	Patient age
Sex	Male/Female
BP	Blood Pressure (LOW, NORMAL, HIGH)
Cholesterol	Cholesterol Level (LOW, NORMAL, HIGH)
Na_to_K	Sodium-to-Potassium Ratio
Drug	Target variable
Project Workflow
Task 1: Exploratory Data Analysis (EDA)

Performed the following analyses:

Displayed first 5 rows
Checked dataset shape
Inspected data types
Checked missing values
Generated statistical summary
Analyzed target variable distribution
Task 2: Data Preprocessing
Encoded categorical features
Encoded target labels using LabelEncoder
Split data into:
Features (X)
Target (y)
Feature Encoding
BP and Cholesterol → Ordinal Encoding
Sex → One-Hot Encoding
Numerical Features → Standard Scaling
Task 3: Train-Test Split

Dataset was divided into:

Training Set: 70%
Testing Set: 30%
train_test_split(
    X,
    y,
    train_size=0.7,
    test_size=0.3,
    random_state=37
)
Task 4: Machine Learning Models

The following classification models were trained:

Logistic Regression
Decision Tree Classifier
Random Forest Classifier
K-Nearest Neighbors (KNN)
Support Vector Machine (SVM)
Task 5: Model Evaluation

Each model was evaluated using:

Accuracy Score
Confusion Matrix
Classification Report
from sklearn.metrics import (
    accuracy_score,
    confusion_matrix,
    classification_report
)
Task 6: Model Comparison

A comparison table was created to rank models based on accuracy.

Example:

Model	Accuracy
Random Forest	Highest
Decision Tree	Very High
KNN	Competitive
SVM	Good
Logistic Regression	Good
Task 7: Prediction on New Patients

The trained model was tested on unseen patient records.

Example:

new_patients = pd.DataFrame({
    'Age': [20, 47, 50, 25, 72],
    'Sex': ['F', 'M', 'F', 'M', 'F'],
    'BP': ['LOW', 'HIGH', 'HIGH', 'NORMAL', 'LOW'],
    'Cholesterol': ['NORMAL', 'HIGH', 'HIGH', 'HIGH', 'NORMAL'],
    'Na_to_K': [25.3, 13.5, 20.0, 9.5, 11.2]
})

The model predicts the most suitable drug for each patient.

Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
Scikit-Learn
Project Structure
├── Drug.ipynb
├── drug200.csv
├── README.md
Key Findings
The dataset is relatively balanced.
Tree-based models performed exceptionally well.
Ordinal Encoding improved handling of BP and Cholesterol categories.
Proper preprocessing reduced the risk of data leakage.
Random Forest emerged as the most reliable model due to its strong performance and robustness.
Future Improvements
Hyperparameter tuning using GridSearchCV
Cross-validation
Feature importance analysis
Model deployment using Flask or Streamlit
Interactive prediction dashboard
