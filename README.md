# Module25
**Final Project for Machine Learning &amp; AI Certification**

**Model Card** 

Dataset from Kaggle: **Disease Risk from Daily Habits**

https://www.kaggle.com/datasets/mahdimashayekhi/disease-risk-from-daily-habits

About Dataset
🧠 Lifestyle and Health Classification Dataset
This dataset contains detailed lifestyle and biometric information from 100,000 individuals. The goal is to predict the likelihood of having a disease based on habits, health metrics, demographics, and psychological indicators.

📦Dataset Overview
Rows: 100,000 individuals
Columns: 40 features + 1 target
Target: target → Binary classification:

healthy
diseased
Imbalanced: ~70% healthy, ~30% diseased

Data Types: Numerical, categorical, ordinal
  
🎯 Target Definition
The target column indicates whether an individual is diagnosed with a certain disease or not. The classification is based on medical and lifestyle indicators derived from the individual’s profile.

🧬 Feature Categories
___________________________________________________________________
🔢 Numerical Features
Feature	            Description
- age	                -> Age of the individual
- bmi	                -> Body Mass Index
- blood_pressure	    -> Systolic blood pressure (mm Hg)
- cholesterol	        -> Cholesterol level (mg/dL)
- heart_rate	        -> Resting heart rate (bpm)
- glucose	Blood       -> glucose level
- insulin	Blood       -> insulin level
- calorie_intake	    -> Daily average calorie consumption
- sugar_intake	      -> Daily sugar intake (grams)
- screen_time	        -> Daily screen time (hours)
- stress_level	      -> Self-reported stress level (0-10 scale)
- mental_health_score	-> Self-reported mental well-being score (0-10 scale)
- training_hours	    -> Weekly training/exercise hours
  
_____________________________________________________________
🧩 Categorical Features
Feature	            Description
- gender	            -> Male / Female
- marital_status	    -> Single, Married, Divorced, Widowed
- diet_type	          -> Vegan, Vegetarian, Omnivore, Keto, Paleo
- occupation	        -> Job type or employment status
- sleep_quality	      -> Subjective sleep quality
- mental_health_support-> Access to mental health resources
- exercise_type	      -> None, Cardio, Strength, Mixed
- device_usage	      -> Device usage level
- healthcare_access	  -> Ease of access to healthcare insurance	Has health insurance or not
- family_history	    -> Family history of disease
- sunlight_exposure	  -> Daily sunlight exposure (Low/Med/High)
- pet_owner	Owns pets ->(Yes/No)
- caffeine_intake	    -> Caffeine consumption level
- meals_per_day	      -> Number of meals consumed per day


📌 Notes
This is not a medical diagnosis tool. It's designed for educational, academic, and research purposes.
Columns like bmi_triple and bmi_duplicate are intentionally designed for students to explore feature redundancy and correlation.
The target was not blindly assigned; label logic respects the underlying feature patterns.

📂 File
health_lifestyle_dataset.csv: Full dataset with 100,000 rows and 48 columns (including the target).

________________________________________________________________________________________________________________
**Introduction**
This project outlines a comprehensive, end-to-end machine learning workflow aimed at developing a robust predictive model to classify subjects as either 'healthy' or 'diseased'. The core objective was to move systematically from raw data to a fully optimized and evaluated classifier. The process was segmented into distinct phases: initial data preprocessing and exploratory analysis, model selection and training, and finally, hyperparameter tuning to maximize predictive accuracy. This structured approach ensures that the final model is not only functional but also well-understood and fine-tuned for the specific classification task at hand.

**Data Preprocessing and Exploratory Analysis 📊**
The initial phase focused on laying a solid foundation for the modeling process. The first script handled the essential setup, beginning with the importation of critical Python libraries such as Pandas for data manipulation and Matplotlib/Seaborn for visualization. The dataset was then loaded into memory, and an initial assessment was performed by printing the head of the DataFrame. This was followed by a crucial data cleaning and preparation stage, designed to handle any inconsistencies, missing values, or formatting issues that could negatively impact model performance.

To gain a deeper understanding of the underlying data structure and the relationships between variables, an exploratory data analysis (EDA) was conducted. A key component of this was the creation of a scatter plot matrix, or pair plot. This powerful visualization technique plots every feature against every other feature. By setting the hue parameter to the 'target' column, the data points were colored based on whether they belonged to the 'healthy' or 'diseased' class. This immediately provided visual cues about potential correlations, feature distributions, and the degree of separation between the two classes, offering valuable insights for the subsequent modeling steps.

**Model Selection, Training, and Optimization 🚀**
For the predictive task, a Random Forest Classifier was chosen. This ensemble learning method is known for its high accuracy, robustness against overfitting, and ability to handle complex, non-linear relationships in data. Although Random Forest models are not strictly sensitive to the scale of features, a feature scaling step was implemented as a best practice. This standardizes the range of the independent variables, which can lead to more stable and faster convergence during training, and is essential if comparing the model's performance against other algorithms like Support Vector Machines or Logistic Regression.

After initializing the Random Forest Classifier, the final and most critical phase was hyperparameter tuning. To avoid suboptimal performance from using default parameters, RandomizedSearchCV was employed. This technique efficiently searches for the best combination of model hyperparameters by sampling a fixed number of parameter settings from specified distributions. By systematically exploring different configurations for parameters like the number of trees in the forest, the maximum depth of each tree, and the number of features to consider at each split, RandomizedSearchCV helps to identify the optimal model architecture that yields the highest performance on unseen data. This final step ensures the model is not just trained, but meticulously tuned for the classification challenge.
________________________________________________________________________________________________________________

**Summary of Findings**
This feature importance chart is much more meaningful than the previous one. The fact that the importance scores are more evenly distributed and that the model is (presumably) no longer predicting only one class indicates that the class_weight parameter was successful. 

The model is now actively trying to find the subtle signals that differentiate between 'healthy' and 'diseased' outcomes.

What the Chart Shows (can be viewed in Mod25_Capstone_4)

The chart displays the top 15 features that the tuned Random Forest model found most useful for making its predictions. The "Importance Score" on the x-axis represents the relative contribution of each feature to the model's decision-making process.
The top five most influential factors, according to your model, are:
- work_hours
- glucose
- sugar_intake
- cholesterol
- sleep_hours

**📣Conclusions and Predictions**

Lifestyle and Metabolic Factors are Key: The most significant conclusion is that a combination of lifestyle choices and key metabolic indicators are the primary drivers of the health outcomes in your dataset. Factors like work_hours, sugar_intake, and sleep_hours are behavioral, while glucose and cholesterol are direct physiological measurements. This suggests a strong link between daily habits and metabolic health.
work_hours is a Powerful, Complex Predictor: It's interesting that work_hours is the most important feature. This is likely a proxy for several other unmeasured factors. For example, high work hours could correlate with higher stress, less time for exercise, poorer diet choices, and disrupted sleep, all of which are known to impact health.
Diet is a Major Contributor: The high importance of glucose, sugar_intake, and cholesterol strongly indicates that diet is a critical component in distinguishing between the 'healthy' and 'diseased' groups in your data. The model has learned that these values are significant predictors.
Predictions can be made based on a holistic view: A key prediction from this analysis is that you cannot determine someone's health status based on a single factor alone. The model needs a combination of many features to make an accurate prediction. For instance, knowing someone's glucose level is useful, but knowing their glucose, work_hours, and sleep_hours together is much more powerful. This highlights the interconnectedness of these lifestyle and health factors.
