 # Student Performance Factors – Machine Learning Project

## Project Documentation

---

## Project Overview

This project focuses on understanding the factors that influence student performance using Machine Learning models and tools.  
The main goal of this project is not only prediction, but also to understand model behavior, especially in terms of underfitting, overfitting, and generalization.

The dataset used in this project is taken from Kaggle and is titled “Student Performance Factors”.

---

## Dataset Understanding

We began by exploring the dataset to understand:

- The structure of the data  
- The usefulness of each feature  
- Which features could help in predicting student exam scores  

The dataset contains a mix of categorical and numerical features, including academic, demographic, and behavioral attributes.

Target Variable: `Exam_Score`

---

## Data Cleaning and Preprocessing

### Handling Missing Values
- Checked the dataset for missing values.
- Missing categorical values were filled using the most frequent value.
- Although `SimpleImputer` could be used, manual handling was chosen for better conceptual understanding.

### Data Type Validation
- Ensured all features were in the correct format.
- Converted categorical variables where required.

---

## Exploratory Data Analysis (EDA)

To understand the dataset visually, several plots were created:

- Heatmap  
  Used to analyze correlations between features and understand how strongly they are related.

- Count Plots  
  - Gender distribution  
  - Tutoring sessions by gender  

- Exam Score vs Sleep Hours (by Gender)  
  Helped in gaining insights into how sleep duration may affect performance.

EDA helped build intuition before applying machine learning models.

---

## Feature Encoding and Preparation

Machine learning models require numerical input, so categorical variables were encoded carefully.

### Encoding Techniques Used
- Ordinal Encoding  
  Used for ordered features such as motivation level, parental involvement, and teacher quality.

- One-Hot Encoding  
  Used for nominal features such as gender, school type, and internet access.

A ColumnTransformer was used to apply different encoders to different feature groups, ensuring clean and readable preprocessing logic.

After encoding:
- The transformed data (NumPy array) was converted into a DataFrame.
- Encoded features were concatenated with scaled numerical features.

This completed the feature extraction and feature selection phase.

---

## Modeling

### Linear Regression
- Used as a baseline model.
- Evaluation metrics:
  - Mean Squared Error (MSE)
  - Mean Absolute Error (MAE)
  - R² Score

Observation:  
The model performed better on testing data than training data, indicating underfitting.  
This showed that the model was too simple to capture underlying patterns.

---

### Polynomial Regression (Degree = 2)
To reduce bias, polynomial features of degree 2 were introduced.

Results:
- Training R² approximately 73 percent
- Testing R² approximately 76 percent

The model captured non-linear relationships effectively and showed good generalization.

This became the best-performing model.

---

### Polynomial Regression (Degree = 3)
Polynomial regression with degree 3 was tested for experimentation and learning.

Observation:
- Training performance remained high.
- Testing performance dropped sharply.

This indicated a clear case of overfitting (high variance).

---

### Ridge Regression (Applied to Degree 3 Model)
To control overfitting, Ridge Regression was applied.

- Different values of alpha were tested.
- Increasing alpha reduced variance.
- Training and testing scores moved closer.

At alpha equal to 10000:
- Training R² approximately 67 percent
- Testing R² approximately 69 percent

However, this performance was still worse than the degree-2 polynomial model.

---

## Final Model Selection

After evaluating all models, Polynomial Regression with degree 2 was selected as the final model because:
- It achieved the highest test performance.
- It showed minimal train–test gap.
- It generalized better than more complex models.

This confirms that increasing complexity does not always improve performance.

---

## Key Learnings

- Data preprocessing is the backbone of machine learning.
- Underfitting occurs when the model is too simple.
- Overfitting occurs when the model is unnecessarily complex.
- Regularization helps control variance but cannot fix poor model choice.
- The best model is the one that generalizes well, not the one with the highest training score.

---

## Goals Achieved Through This Project

- Learned data cleaning and exploratory data analysis techniques.
- Prepared real-world data for machine learning models.
- Understood categorical encoding strategies.
- Explored bias–variance tradeoff in depth.
- Applied Ridge Regression correctly.
- Learned how to evaluate and select the best model.

---

## Conclusion

This project demonstrates a complete machine learning workflow, from data understanding to final model selection.  
The focus was on learning, reasoning, and model behavior rather than only accuracy.

As a first machine learning project, this work provides a strong foundation and will be extended further as more advanced models are learned.

---

## Author

Ashmit Shukla  
First Machine Learning Project

Feedback and suggestions are always welcome.
