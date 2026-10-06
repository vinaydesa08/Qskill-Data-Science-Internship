# Student Performance Analysis & Prediction

## Project Overview

This project analyzes student performance data to identify the factors associated with exam scores and uses machine learning to predict student exam performance.

The analysis includes data cleaning, exploratory data analysis (EDA), visualization, correlation analysis, feature engineering, and machine learning using a Random Forest Regression model.

The project was completed as part of the QSkill Data Science Internship.

## Problem Statement

Student academic performance can be influenced by several factors such as attendance, study hours, previous scores, tutoring sessions, access to resources, parental involvement, and other learning-related factors.

The objective of this project is to analyze these factors, understand their relationship with exam scores, and build a machine learning model that can predict student exam performance.

## Objectives

- Analyze the student performance dataset.
- Clean and preprocess the data.
- Handle missing values and invalid records.
- Explore factors related to student exam scores.
- Visualize important patterns and relationships.
- Identify important features using correlation analysis and machine learning.
- Build a Random Forest Regression model to predict exam scores.
- Evaluate the model using MAE, RMSE, and R² score.

## Dataset Information

The dataset used for this project is `StudentPerformanceFactors.csv`.

It contains **6,607 student records** and **20 columns** describing academic, personal, and learning-related factors.

### Target Variable

- `Exam_Score` — Final exam score of the student.

### Important Features

- `Hours_Studied`
- `Attendance`
- `Previous_Scores`
- `Tutoring_Sessions`
- `Sleep_Hours`
- `Physical_Activity`
- `Motivation_Level`
- `Parental_Involvement`
- `Access_to_Resources`
- `Family_Income`
- `Teacher_Quality`
- `Parental_Education_Level`
- `Internet_Access`
- `Extracurricular_Activities`
- `Peer_Influence`
- `School_Type`
- `Learning_Disabilities`
- `Distance_from_Home`
- `Gender`

## Tools and Technologies

- **Python** — Data analysis and machine learning
- **Pandas** — Data manipulation and cleaning
- **NumPy** — Numerical operations
- **Matplotlib** — Data visualization
- **Seaborn** — Correlation heatmap
- **Scikit-learn** — Data preprocessing, model training, and evaluation
- **Jupyter Notebook** — Development environment
- **VS Code** — Project development

## Data Cleaning and Preprocessing

The dataset was checked and cleaned before performing exploratory analysis and machine learning.

### Missing Values

The dataset initially contained **235 missing values**:

- `Teacher_Quality` — 78 missing values
- `Parental_Education_Level` — 90 missing values
- `Distance_from_Home` — 67 missing values

The missing values were handled using the **mode** of the respective columns.

After cleaning, the dataset contained **0 missing values**.

### Duplicate Records

The dataset was checked for duplicate rows.

- Duplicate rows found: **0**

Therefore, no duplicate records were removed.

### Invalid Exam Score

During data validation, one record had an `Exam_Score` of **101**, which is outside the expected 0–100 range.

The invalid value was corrected to **100**.

### Final Dataset

After preprocessing:

- **Rows:** 6,607
- **Columns:** 20
- **Missing values:** 0
- **Duplicate rows:** 0
- **Target variable:** `Exam_Score`

## Exploratory Data Analysis

Exploratory Data Analysis was performed to understand the distribution of exam scores and identify relationships between different student-related factors and exam performance.

### Overall Exam Score

- **Average Exam Score:** 67.24
- **Highest Exam Score:** 100
- **Lowest Exam Score:** 55
- **Median Exam Score:** 67.00

### Study Hours

The analysis showed a generally increasing pattern between hours studied and average exam score. Students with higher study hours generally had higher average exam scores, although some fluctuations were present.

Visualization:

`study_hours_vs_score.png`

### Attendance

Attendance showed a clear positive association with average exam score. As attendance increased, the average exam score generally increased.

Visualization:

`attendance_vs_score.png`

### Previous Scores

Previous scores showed a modest positive relationship with current exam scores. Students with higher previous scores generally had slightly higher average current exam scores.

Visualization:

`previous_scores_vs_score.png`

### Motivation Level

Average exam scores across motivation levels were:

- Low: **66.75**
- Medium: **67.33**
- High: **67.70**

The differences between the groups were relatively small.

Visualization:

`motivation_vs_score.png`

### Parental Involvement

Average exam scores across parental involvement levels were:

- Low: **66.36**
- Medium: **67.10**
- High: **68.09**

The analysis showed a gradual increase in average exam score across these groups.

Visualization:

`parental_involvement_vs_score.png`

### Access to Resources

Average exam scores across resource-access levels were:

- Low: **66.20**
- Medium: **67.13**
- High: **68.09**

The results showed an increasing pattern across the three resource-access levels.

Visualization:

`resources_vs_score.png`

### Tutoring Sessions

The analysis showed that average exam scores generally increased with the number of tutoring sessions, although there were fluctuations at higher session counts.

Visualization:

`tutoring_vs_score.png`

### Correlation Analysis

A correlation heatmap was created to examine relationships between numerical variables.

The correlations with `Exam_Score` were:

| Feature | Correlation |
|---|---:|
| Attendance | 0.58 |
| Hours Studied | 0.45 |
| Previous Scores | 0.18 |
| Tutoring Sessions | 0.16 |
| Physical Activity | 0.03 |
| Sleep Hours | -0.02 |

Among the numerical variables analyzed, **Attendance and Hours Studied had the strongest positive correlations with Exam_Score**.

> Correlation indicates association between variables and does not by itself establish causation.

Visualization:

`correlation_heatmap.png`

## Machine Learning

A Random Forest Regression model was used to predict the `Exam_Score`.

### Data Preparation

The target variable was separated from the input features:

- **Features:** 19
- **Target:** `Exam_Score`

Categorical variables were converted into numerical features using **One-Hot Encoding**.

After encoding:

- **Encoded features:** 40

The dataset was divided into training and testing sets:

- **Training data:** 80% — 5,285 records
- **Testing data:** 20% — 1,322 records

### Model Used

**Random Forest Regressor**

The model was configured with:

- `n_estimators = 100`
- `random_state = 42`

### Model Evaluation

The trained model was evaluated using Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R² Score.

| Metric | Result |
|---|---:|
| MAE | **1.09** |
| RMSE | **2.17** |
| R² Score | **0.6684** |

### Interpretation

- The **MAE of 1.09** indicates that the model's predictions differed from the actual exam scores by about 1.09 marks on average.
- The **RMSE of 2.17** represents the prediction error while giving greater weight to larger errors.
- The **R² score of 0.6684** indicates that the model explains approximately 66.84% of the variation in exam scores.

### Actual vs Predicted Scores

The actual versus predicted plot was created to visually compare the model's predictions with the actual exam scores.

Visualization:

`actual_vs_predicted.png`

## Feature Importance

Feature importance was extracted from the Random Forest model to identify which features contributed most to the model's predictions.

### Top 10 Important Features

| Feature | Importance |
|---|---:|
| Attendance | 0.3752 |
| Hours Studied | 0.2388 |
| Previous Scores | 0.0816 |
| Tutoring Sessions | 0.0325 |
| Physical Activity | 0.0252 |
| Sleep Hours | 0.0248 |
| Access to Resources — High | 0.0189 |
| Parental Involvement — High | 0.0178 |
| Parental Involvement — Low | 0.0134 |
| Family Income — High | 0.0107 |

The model relied most heavily on Attendance and Hours Studied, followed by Previous Scores.

Feature importance represents the contribution of features to the model's predictions and does not by itself establish a causal relationship.

Visualization:

`feature_importance.png`

## Key Insights

- Attendance had the strongest correlation with Exam_Score among the numerical variables, with a correlation of 0.58.
- Hours Studied had the second strongest correlation with Exam_Score, with a correlation of 0.45.
- Previous Scores showed a modest positive association with current Exam_Score.
- Average exam scores generally increased with higher study hours.
- Higher attendance was generally associated with higher average exam scores.
- Students with higher parental involvement and better access to resources had slightly higher average exam scores.
- The Random Forest model identified Attendance and Hours Studied as the two most important features for prediction.
- The model achieved an MAE of 1.09, RMSE of 2.17, and R² score of 0.6684.

## Conclusion

This project analyzed student performance data to understand the factors associated with exam scores and developed a machine learning model for exam score prediction.

The exploratory analysis showed that Attendance and Hours Studied had notable positive associations with Exam_Score. The Random Forest Regression model was able to predict exam scores with an MAE of 1.09 and an R² score of 0.6684.

The analysis demonstrates how data analysis and machine learning can be used to identify patterns in student performance and develop predictive models based on academic and learning-related factors.

## Future Scope

- Test additional machine learning algorithms such as Linear Regression, Decision Tree Regression, and Gradient Boosting.
- Perform hyperparameter tuning to improve model performance.
- Explore additional feature engineering techniques.
- Develop an interactive dashboard for exploring student performance.
- Build a simple application that allows users to enter student information and receive a predicted exam score.
- Evaluate the model on new and larger datasets.

## Project Structure

```text
Qskill_student_performance_analysis/
├── Dataset/
│   └── StudentPerformanceFactors.csv
├── Notebook/
│   └── Student_Performance_Analysis.ipynb
├── Readme/
│   └── README.md
└── Visualization/
    ├── study_hours_vs_score.png
    ├── attendance_vs_score.png
    ├── previous_scores_vs_score.png
    ├── motivation_vs_score.png
    ├── parental_involvement_vs_score.png
    ├── resources_vs_score.png
    ├── tutoring_vs_score.png
    ├── correlation_heatmap.png
    ├── actual_vs_predicted.png
    └── feature_importance.png