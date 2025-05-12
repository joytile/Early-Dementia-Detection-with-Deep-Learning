# Early Dementia Detection with Deep Learning
![GitHub](https://img.shields.io/badge/Language-Python-blue)
![GitHub](https://img.shields.io/badge/Model-Deep_Learning-purple)
![GitHub](https://img.shields.io/badge/Library-Scikit_Learn-Green)

## Project Overview

This project shows an end-to-end machine learning pipeline for the prediction of dementia using a publicly available kaggle dataset.

## Dataset 📂
The dataset (`dementia_data.csv`) is available in this repository and was sourced from Kaggle. It contains features ranging from clinical scores to demographics and lifestyle attributes, useful for studying dementia onset and progression.


## Methodology 
![Framework](https://github.com/joytile/Early-Dementia-Detection-with-Deep-Learning/blob/main/Framework.png)

### 1. Exploratory Data Analysis 🔭
- **Descriptive Statistics**: Examining the characteristics of the data
- **Variable Analysis**: Visualizing each feature to understand it better

  ### Key Insights💡
  **🧍 Demographic Distribution**
  - The target variable 'Dementia' is relatively balanced, indicating no major class imbalance issue.
    ![Framework](https://github.com/joytile/Early-Dementia-Detection-with-Deep-Learning/blob/main/dementia_outcome.jpg)
  - Dementia cases are evenly distributed across genders, with both males and females having comparable rates of positive and negative outcomes.
    
    ![Chart](https://github.com/joytile/Early-Dementia-Detection-with-Deep-Learning/blob/main/gender.jpg)
  
  **🧠 Clinical Indicators**
  - Finding: The Dosage (mg) and Prescription variables are only populated for patients diagnosed with dementia. Their presence is a strong proxy indicator for a positive dementia diagnosis and may cause data leakage if not handled carefully in modeling.
  - Cognitive score sharply separates the classes: all dementia patients score below 8, while non-dementia patients score between 8 and 10. This variable appears to be highly predictive.

    ![Chart](https://github.com/joytile/Early-Dementia-Detection-with-Deep-Learning/blob/main/cognitive_scores.jpg)
  - All non-dementia patients are also not depressed, suggesting a strong correlation between depression and dementia presence in this dataset.
  
  **🎓 Socio-Educational Patterns**
  - Primary school education is the most common educational level and has the highest number of dementia patients
  - Patients with Diploma/Degree education levels show the lowest dementia incidence.
    ![Chart](https://github.com/joytile/Early-Dementia-Detection-with-Deep-Learning/blob/main/educational_level.jpg)
  
### 2. Data Preprocessing and Feature Engineering 🛠️
- **Handling Missing Values**: Filling in missing values with null and dropping missing values where necessary
- **Variable encoding**: Encoding boolean and other categorical variables to allow the model to understand them.
- **Dropping features**: Removing features that could introduce data leakage to our model.
- **Dimensionality Reduction**: Made use of Principal Component Analysis (PCA) to reduce dimensionality and handle multicollinearity
  
### 3. Model Development
- **Modeling Techniques:** Evaluated three main approaches:
  - Artificial Neural Network (ANN) with Bayesian hyperparameter tuning (optimized for recall)
  - K-Nearest Neighbors (KNN)
  - Decision Tree Classifier
  - AdaBoost Classifier

### 4. Model Evaluation
- **Metrics**: Accuracy, Precision, Recall, F1-Score, Confusion Matrix
- Comparative Analysis of ANN, KNeighbors and ensemble classifiers
  ![Chart](https://github.com/joytile/Early-Dementia-Detection-with-Deep-Learning/blob/main/model_comp.png)


# Recommendations 👌
- Prioritize Cognitive Assessments in Screening
  Low cognitive test scores (below 8) are strong early signs of dementia. Prioritize these tests in regular health checkups.
- Watch for Depression
  In this dataset, all patients without dementia also had no depression. Screening for depression can help flag higher-risk individuals.
- Pay Extra Attention to Lower Education Groups
  People with only primary education had the highest dementia rates. Extra monitoring may help detect symptoms earlier.
