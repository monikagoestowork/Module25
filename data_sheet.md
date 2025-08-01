### **Datasheet: Health & Lifestyle Classification Dataset**

This document provides a detailed overview of the dataset used in the Health & Lifestyle Classification project.

### **Motivation**

* **For what purpose was the dataset created?**
    The dataset was created to develop a machine learning model capable of classifying individuals as 'healthy' or 'diseased'. It serves as the foundation for exploring the relationships between various lifestyle factors and health outcomes, and for training and evaluating a predictive classifier. Taken from Kaggle https://www.kaggle.com/datasets/mahdimashayekhi/disease-risk-from-daily-habits

### **Composition**

* **What do the instances that comprise the dataset represent?**
    This dataset contains detailed lifestyle and biometric information from 100,000 individuals. The goal is to predict the likelihood of having a disease based on habits, health metrics, demographics, and psychological indicators.

* **How many instances are there in total?**
    Kaggle does not specify the total number of instances before cleaning, but load and process the data from a single CSV file that was downloaded and accessed locally.

* **What data does each instance consist of?**
    Each instance consists of 48 features. The scripts focus on a subset of key numeric features for analysis and visualization, including:
    * `age`
    * `bmi` (Body Mass Index)
    * `blood_pressure`
    * `calorie_intake`
    * `stress_level`
    The dataset also contains a `target` column, which serves as the label for classification ('healthy' or 'diseased').

* **Is any information missing from individual instances?**
    Yes. The initial data contains missing (null) values. The scripts handle this by identifying the nulls and then dropping any rows that contain them before analysis or modeling.

### **Collection Process**

* **How was the data collected?**
    The method of data collection (e.g., surveys, clinical trials, electronic health records) is not described in the provided scripts.

* **Who was involved in the data collection process?**
    This information is not available in Kaggle.

* **Over what timeframe was the data collected?**
    This information is not available in Kaggle.


### **Preprocessing/Cleaning/Labeling**

* **Was the raw data cleaned or preprocessed?**
    Yes. The following preprocessing steps were applied across the scripts:
    * **Handling Missing Values**: Rows with null values were removed from the dataset.
    * **Label Encoding**: The categorical `target` variable ('healthy', 'diseased') was converted into numerical format (1 and 0, respectively) for model training.
    * **Normalization/Scaling**:
        * **L2 Normalization** was applied in one script to scale the data for exploratory analysis.
        * **StandardScaler** was used in the modeling script to standardize the features (zero mean, unit variance) before training the Random Forest model.

* **Is the software used for preprocessing available?**
    Yes, the preprocessing was performed using publicly available Python libraries, including **Pandas** and **scikit-learn**.

### **Uses**

* **Has the dataset been used for any tasks already?**
    Yes, the dataset has been used for:
    1.  **Exploratory Data Analysis**: To understand the relationships between features and health outcomes using scatter plot matrices and violin plots.
    2.  **Predictive Modeling**: To train and evaluate a **Random Forest Classifier** to predict whether an individual is 'healthy' or 'diseased'.

* **Is there a recommended split of the data?**
    Yes, the modeling script recommends and implements a standard training and testing split to evaluate model performance on unseen data.

* **Are there any tasks for which the dataset should not be used?**
    The dataset should be used with caution for giving real-world medical advice. The model provides a prediction based on statistical patterns and is not a substitute for a professional medical diagnosis.

### **Distribution**

* **How will the dataset be distributed?**
    The dataset is contained in a single CSV file named `health_lifestyle_classification.csv`.

* **Will the dataset be updated?**
    This information is not available in Kaggle.

### **Maintenance**

* **Who is responsible for maintaining the dataset?**
    As this is for a capstone project, the project author (M Mandal) is the current maintainer of the dataset and the associated analyses.
