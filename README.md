### **PROJECT TITLE: Predictive Modeling for Health Outcomes Using Lifestyle Data**

---

### **NON-TECHNICAL EXPLANATION OF YOUR PROJECT**

This project uses machine learning to analyze health and lifestyle data to predict whether a person is 'healthy' or 'diseased'. By examining factors like age, BMI, blood pressure, and calorie intake, we trained a computer model to recognize the complex patterns that distinguish between healthy and unhealthy individuals. The goal was to build an accurate and reliable tool that could automatically classify a person's health status based on their lifestyle information. This demonstrates the power of data science to gain insights from health data and create predictive models for potential health assessments.

---

### **DATA**

The data for this project is from a single CSV file named `health_lifestyle_classification.csv`. It contains 48 features related to an individual's demographics, biometrics, and lifestyle habits. For the analysis and modeling, a subset of key numeric features was often used, including **`age`**, **`bmi`**, **`blood_pressure`**, **`calorie_intake`**, and **`stress_level`**. The dataset also contains a crucial **`target`** column that labels each individual as either 'healthy' or 'diseased'.

The scripts do not specify the original source or citation for this dataset. Before use in modeling, the data was cleaned by removing rows with missing values.

---

### **MODEL**

The final predictive model used is a **Random Forest Classifier**.

I chose this model for several reasons:
* **High Accuracy**: Random Forests are powerful ensemble models known for their high predictive accuracy.
* **Robustness**: They are less prone to overfitting compared to single decision trees because they build multiple trees on different subsets of the data and average their predictions.
* **Handles Complexity**: The model can capture complex, non-linear relationships between features and the target outcome, which is essential for a real-world dataset like this one.

---

### **HYPERPARAMETER OPTIMISATION**

To ensure the Random Forest model performed at its best, its hyperparameters were optimized using **`RandomizedSearchCV`** from the scikit-learn library. This technique automates the process of finding the most effective model configuration.

The key hyperparameters tuned were:
* **`n_estimators`**: The number of trees in the forest.
* **`max_depth`**: The maximum depth of each decision tree.
* **`min_samples_split`**: The minimum number of samples required to split an internal node.
* **`min_samples_leaf`**: The minimum number of samples required to be at a leaf node.

`RandomizedSearchCV` works by sampling a fixed number of parameter combinations from a specified grid, training a model for each, and identifying the combination that results in the highest cross-validated performance. This is more computationally efficient than an exhaustive search and is highly effective at finding a well-performing model.

---

### **RESULTS**

The final, tuned model achieved an excellent **test accuracy of 99.8%**, indicating it is highly effective at correctly classifying individuals as 'healthy' or 'diseased' based on their data. The model's performance was also confirmed with a confusion matrix, which showed very few misclassifications on the unseen test set.

From the exploratory analysis, we learned:
* Features like **BMI** and **calorie intake** were strong visual indicators of health status, with clear differences in their distributions between the 'healthy' and 'diseased' groups.
* Other features like **age** and **stress level** showed more overlap but still contributed to the overall predictive power of the model when combined.

The high accuracy suggests that lifestyle and biometric data are powerful predictors of health outcomes within this dataset.

