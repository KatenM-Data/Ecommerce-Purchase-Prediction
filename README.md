# 🛒 E-Commerce Purchase Intent Prediction (Machine Learning)

## 🎯 Executive Summary
The objective of this project was to develop a predictive model for a leading e-commerce platform to identify high-potential customers. By analysing user session behaviour, the model predicts the likelihood of a purchase, allowing the marketing team to optimise ad spend and reduce unnecessary marketing overhead by excluding low-intent users from expensive re-targeting campaigns.

## 🛠️ Technical Stack & Data Engineering
*   **Language:** Python 3.x
*   **Libraries:** Scikit-Learn (Machine Learning), Pandas (Data Manipulation), NumPy (Numerical Analysis), Seaborn/Matplotlib (Visualisation).
*   **Algorithm:** **Random Forest Classifier** — chosen for its versatility in handling both categorical and continuous variables while remaining robust against overfitting.

## 🏗️ Model Development Pipeline

### 1. Feature Analysis & Selection
The model utilises five key predictive features to determine purchase intent:
*   **Continuous Features:** Age and Time Spent on Site.
*   **Categorical Features:** Gender, Pages Viewed, and Ad Clicked status.
*   **Target Variable:** Purchase (1 = Yes, 0 = No).

### 2. Model Training & Reproducibility
*   **Data Split:** Implemented a **70/30 Train/Test split** to ensure the model was validated on unseen data.
*   **Reproducibility:** Utilised `random_state=42` to ensure consistent results across different environments.
*   **Optimisation:** Configured `n_estimators=100` and `max_depth=10` to balance model accuracy with computational efficiency.

### 3. Performance Evaluation (The "BS" Detector)
*   **Accuracy:** The model achieved a **90% accuracy rate** on the test set.
*   **Confusion Matrix:** Utilised to compare predicted vs. actual classes, ensuring high precision in identifying real buyers.

---
*This project was completed as part of the Professional Certificate in Data Analytics & AI (Code Institute).*

## 📸 Technical Audit & Visualisation

### 1. Data Source Inspection
A sample of the cleaned dataset used to train the Random Forest model, demonstrating the structure of features and labels.
![Data Sample](ml_data_head.png)

### 2. Model Performance (Confusion Matrix)
The Seaborn heatmap below visualises the accuracy of the predictions. By identifying True Negatives correctly, the business can avoid wasting budget on uninterested users.
![Confusion Matrix](ml_heatmap.png)

### 3. Full Technical Execution (Audit Log)
This screenshot captures the final evaluation metrics and classification report, proving 90% accuracy.
![Model Results](ml_results.png)

## 🔮 Real-World Inference: The "Money-Saving" Logic
To test the model's practical application, I ran a specific "Time-Waster" test case through the engine:
- **Input:** 32yo Female, 15.4 mins on site, 8 pages viewed, clicked ad.
- **Model Prediction:** **[0] - No Purchase.**
- **Business Action:** In a live environment, this user would be **excluded** from high-cost re-targeting ads. By predicting this user wouldn't buy despite their ad click, the model saves the business "Marketing Overhead"—ensuring ad spend is only used on high-probability conversions.

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
