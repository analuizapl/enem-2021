# Enem 2021 - Linear Regression on Student Performance

## Description

This code analyzes the Brazilian National High School Examination (Enem) microdata from 2021 to predict student performance on the final exam based on socioeconomic factors.

## Data
For this analysis, the following data sets were used:
Base | Description
--- | --- 
[ENEM Data 2021](https://download.inep.gov.br/microdados/microdados_enem_2021.zip) | Data on the National Exam applied in 2021 with all the candidate's grades.


## Data Cleaning and Preparation:
1. Reads the Enem microdata CSV file.
2. Renames columns for better readability.
3. Converts categorical columns with letter grades ('A', 'B', 'C', etc.) to numerical values (0, 1, 2, etc.).
4. Handles missing data by dropping rows with missing values (dropna()).
5. Creates dummy variables for categorical columns like gender and parental occupation.
6. Converts some string columns (e.g., 'NU_NOTA_CN') to numeric format for calculations.
7. Creates a new 'NOTA_FINAL' column representing the average of all subject scores.
8. Splits the data into features (X) and target variable (y).
	X: all columns except 'NOTA_FINAL'.
	y: 'NOTA_FINAL' column.
9. Splits the data further into training and testing sets (80%/20% split) using train_test_split for model evaluation.


## Model Building and Evaluation:

1. Trains a linear regression model (modelo_lr) to predict the 'NOTA_FINAL' based on the features in X_train.
2. Generates predictions (y_pred) using the trained model on the training data (X_train).
3. Calculates the feature importances (coefficients) to identify which features have the most significant impact on the model's predictions.
4. Analyzes the top 5 and bottom 5 most important features using bar plots with Seaborn.
5. Creates a scatter plot to visualize the actual vs. predicted values for the training data.
6. Calculates the percentage of points that fall above, below, and exactly on the regression line.

## Preliminary Conclusions from the ENEM Test-Taker Visualization

1. Majority of Test-Takers are Young: The overwhelming majority of students taking the ENEM are in their late teens or early twenties, as expected for a high school exam.

2. Fewer Older Test-Takers: The number of test-takers decreases significantly as age increases. This could be due to various reasons such as returning to education later in life or taking the exam for other purposes like college entrance.

3. Gender Imbalance: There is a notable disparity between the genders, with females outnumbering males by a substantial margin.

	* Quantitative Difference: Approximately 334,092 females are represented compared to 257,297 males.
4. Score Differences Across Subjects: There is a noticeable difference in median scores across subjects.

	* NU_NOTA_REDACAO (Redação): Has the highest median.
	* NU_NOTA_CH (Humanidades): Follows with a slightly lower median.
	* Other Subjects: NU_NOTA_CN, NU_NOTA_LC, and NU_NOTA_MT have relatively lower medians.
5. Impact of Socioeconomic Factors:

	* Positive Impact: Features like ESCOLARIDADE_PAI_A (father's education level) and RENDA_MENSAL_D (household income) have the most significant positive impact on the model's predictions, suggesting these factors are crucial in influencing outcomes.

	* Negative Importance: Features such as ESCOLARIDADE_MAE_A (mother's education level) and QUANT_BANHEIROS (number of bathrooms) have negative importance, implying a negative correlation with the target variable. However, their impact is relatively small compared to the top features.

6. Model Bias: The higher percentage of points below the line suggests a potential underestimation bias in the model, indicating that the model consistently predicts values lower than the actual values.

7. Overfitting Concerns: An R² value of 1.0 in every fold of cross-validation is an impossible scenario in real-world data. It indicates a perfect fit, which is highly unlikely and suggests overfitting.

## Next Steps
Fix overfitting problem
