# 🛒 E-Commerce Purchase Intent Prediction (Machine Learning)

## 🎯 Executive Summary
The objective of this project was to develop a predictive model for a leading e-commerce platform to identify high-potential customers. By analysing user session behaviour, the model predicts the likelihood of a purchase, enabling the marketing team to optimise ad spend and increase overall conversion rates.

## 🛠️ Technical Stack & Data Engineering
*   **Language:** Python 3.x
*   **Libraries:** Scikit-Learn (Machine Learning), Pandas (Data Manipulation), NumPy (Numerical Analysis), Seaborn/Matplotlib (Visualisation).
*   **Algorithm:** **Random Forest Classifier** — chosen for its robustness and ability to handle complex, non-linear relationships while preventing overfitting.

## 🏗️ Model Development Pipeline

### 1. Data Pre-Processing & Feature Selection
Cleaned and structured raw session data, focusing on five key predictive features:
*   **User Demographics:** Age and Gender.
*   **Engagement Metrics:** Time Spent on Site and Pages Viewed.
*   **Marketing Interaction:** Ad Clicked status.

### 2. Model Training & Reproducibility
*   **Data Split:** Implemented a **70/30 Train/Test split** to ensure the model was validated on unseen data.
*   **Consistency:** Utilised `random_state=42` to ensure consistent, reproducible results across different environments.
*   **Optimisation:** Configured `n_estimators=100` and `max_depth=10` to balance model accuracy with computational efficiency.

### 3. Performance Evaluation (The "BS" Detector)
*   **Accuracy:** The model achieved a **90% accuracy rate** on the test set.
*   **Classification Report:** Verified precision and recall to ensure the model effectively identifies actual buyers while minimising "False Positives" (wasted ad spend).

---
*This project was completed as part of the Professional Certificate in Data Analytics & AI (Code Institute).*

## 📸 Technical Audit & Visualisation

### 1. Data Source Inspection
A sample of the cleaned dataset used to train the Random Forest model, demonstrating the structure of features and labels.
![Data Sample](ml_data_head.png)

### 2. Model Performance (Confusion Matrix)
The Seaborn heatmap below visualises the accuracy of the predictions. With only 2 false positives in the test set, the model demonstrates high precision.
![Confusion Matrix](ml_heatmap.png)

### 3. Full Technical Execution (Audit Log)
This screenshot captures the final evaluation metrics and classification report from the Jupyter environment, proving model reliability.
![Model Results](ml_results.png)

### 🧠 Python Logic & Model Configuration
The code below demonstrates the surgical implementation of the predictive engine:

**1. Initialising the Random Forest**
```python
# Initialise and train the random forest classifier
model = RandomForestClassifier(n_estimators=100, max_depth=10, random_state=42)
model.fit(X_train, y_train)
```
**2. Calculating Accuracy Metrics**
code
```Python
# Measure how well the model performed on unseen data
y_pred = model.predict(X_test)
accuracy = accuracy_score(y_test, y_pred)
print(f"Accuracy: {accuracy:.2f}")
```
**3. Predicting New User Intent**

I developed a pipeline to ingest new, raw user data and return an instant "Purchase / No Purchase" prediction.
code
```Python
# Predicting intent for a single user session
# Example: 32yo Female, 15 mins on site, 8 pages viewed, clicked ad.
predicted_purchase = model.predict(new_data)
```
