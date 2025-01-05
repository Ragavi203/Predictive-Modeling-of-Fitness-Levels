# Predictive-Modeling-of-Fitness-Levels

https://colab.research.google.com/drive/1nuWDa-_9hl-0kRtZvUyE1ndyQLnNHoST?usp=sharing

Objective:

The objective of this project is to predict an individual's fitness level based on various features such as daily activity metrics and personal health indicators. The model aims to assist users in understanding the key factors that contribute to their fitness level.

Dataset Overview:  https://www.kaggle.com/datasets/jijagallery/fitlife-health-and-fitness-tracking-dataset

The dataset used for this project includes various features:

duration_minutes: Duration of physical activity in minutes.

age: Age of the individual.

hydration_level: Level of hydration.

daily_steps: Number of steps taken daily.

stress_level: Level of stress.

bmi: Body Mass Index.

resting_heart_rate: Resting heart rate.

Additional categorical features (gender, activity_type, intensity) were also present and encoded using one-hot encoding.

Data Preprocessing:

Handling Missing Values: Rows with missing values were dropped.

Encoding Categorical Variables: One-hot encoding was applied to gender, activity_type, and intensity.

Feature Scaling: StandardScaler was used to standardize the features, which is especially useful for algorithms sensitive to feature scaling like Neural Networks and SVM.

Model Training:

Random Forest Regressor (Initial Model):

Model: RandomForestRegressor

Hyperparameters:

n_estimators: 100

max_depth: 10

random_state: 42

Performance:

RMSE: 4.9067

R² Score: 0.2097

Hyperparameter Tuning:

Approach: RandomizedSearchCV was used to perform hyperparameter tuning with a reduced hyperparameter space to expedite the process.

Best Parameters:

n_estimators: 50

max_depth: 10

min_samples_split: 2

min_samples_leaf: 1

Performance:

RMSE: 4.8813

R² Score: 0.2176

Final Model (Full Dataset):

The best parameters were used to train the model on the entire dataset.

Performance:

RMSE: 4.7764

R² Score: 0.2509

Model Evaluation:

Feature Importance: The most significant feature was daily_steps, followed by duration_minutes, hydration_level, and age.

Predicted Fitness Level: For a new input data point, the model predicted a fitness level of approximately 7.15.

XGBoost Model:

Model: XGBRegressor

Performance:

RMSE: 4.9600

R² Score: 0.1922

The Random Forest model outperformed the XGBoost model in this case.

Conclusions:

The Random Forest Regressor, after hyperparameter tuning, provided the best results with an RMSE of 4.7764 and an R² Score of 0.2509.

daily_steps was identified as the most critical feature influencing the fitness level.

Future improvements could involve more extensive hyperparameter tuning and exploring additional features or data sources to enhance predictive performance.

Next Steps:

Model Deployment: The final model and scaler were saved using joblib for deployment.

Continuous Improvement: Further tuning and testing with more data or additional features could improve model accuracy.

User Interface: Developing an application or interface for users to input their data and receive fitness level predictions.
