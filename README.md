# Module25
**Final Project for Machine Learning &amp; AI Certification**

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

