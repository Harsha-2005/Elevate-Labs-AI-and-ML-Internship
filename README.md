# Elevate-Labs-AI-and-ML-Internship
AI/ML Intenship Tasks Completion 
Of course, Harsha! Here are the key notes summarizing what you learned and accomplished today.



I successfully performed a complete data preprocessing workflow on the Titanic dataset, transforming it from raw data into a clean, model-ready format. Here are the essential steps and concepts you covered:


1. Initial Data Exploration 

The first step in any data project is to understand your material. You learned to:
->Load Data: Use `pandas.read_csv()` to import your dataset.
->Get Basic Info: Use `df.info()` to see the number of entries, column names, and data types (like `int64`, `float64`, `object`).
->Identify Missing Values: Use `df.isnull().sum()` to quickly count how many null (empty) values are in each column. This is crucial for planning your cleaning strategy.


2. Handling Missing Values 

You can't train a model on empty data. You applied three key strategies:
->Mean Imputation (for numbers): You filled the missing `Age` values with the average age of all other passengers. This is a great way to handle missing numerical data without losing the entire row.
->Mode Imputation (for categories): You filled the two missing `Embarked` values with the most common port of embarkation (the mode). This is the standard approach for categorical data.
->Dropping a Column: The `Cabin` column had too much missing information (over 77%). Instead of trying to guess the values, the best strategy was to drop the entire column using `df.drop()`.


3. Encoding Categorical Features 

Machine learning models only understand numbers, not text. You converted text-based categories into a numerical format:
->Mapping (for binary categories): For the `Sex` column, you used a simple map to convert 'male' to `0` and 'female' to `1`.
->One-Hot Encoding (for non-binary categories): For the `Embarked` column (with values 'S', 'C', 'Q'), you created new columns (`Embarked_S`, `Embarked_C`, `Embarked_Q`). A passenger from port 'S' gets a `1` in the `Embarked_S` column and `0` in the others. This prevents the model from assuming an incorrect order or relationship between the ports.
->Dropping Identifiers: Columns like `PassengerId`, `Name`, and `Ticket` were removed because they are unique identifiers and don't provide general patterns for the model to learn.



4. Normalization / Standardization 

You learned how to bring all numerical features to the same scale, which is vital for many ML algorithms.
->Why? Features with large value ranges (like `Fare`) can dominate features with smaller ranges (like `Pclass`). Standardization prevents this bias.
->How? You used `StandardScaler` from scikit-learn. This powerful tool transforms your data so that each numerical feature has a **mean of 0** and a **standard deviation of 1**.


![licensed-image](https://github.com/user-attachments/assets/e2cbc195-cec3-4157-8c8c-5b10eeec5a07)




5. Outlier Detection and Removal 

Outliers are extreme values that can skew your model's learning. You learned a robust method to handle them:
->Visualization: You used **boxplots** to visually identify the data points that fall far outside the normal range for `Age` and `Fare`.
->IQR Method:** You used the **Interquartile Range (IQR)** to mathematically define and remove outliers. This method calculates the range between the 25th (Q1) and 75th (Q3) percentiles and removes any data point that falls too far below Q1 or above Q3. This made your dataset more robust and reliable.

Great job today! You've mastered the foundational steps of preparing data for any machine learning project.
