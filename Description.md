# **Liver Cirrhosis Stage Prediction Project**

## **Project Overview**
This project aims to predict the stage of liver cirrhosis using a dataset containing various medical features. The goal is to train machine learning models to predict the disease's progression. After experimenting with several algorithms, the **Random Forest** model was chosen as the final model due to its effectiveness in handling complex data relationships.

---

## **Step 1: Import Libraries**
In this step, we import the necessary libraries required for the project. These include libraries for data manipulation, machine learning, and model evaluation. The libraries we use are essential for tasks such as data preprocessing, training models, and visualizing results.

---

## **Step 2: Data Gathering**
Here, the dataset is loaded from a CSV file into a DataFrame for further analysis. The dataset includes various features related to liver cirrhosis, and it's crucial to ensure that the data is clean and ready for the next steps.

---

## **Step 3: Exploratory Data Analysis (EDA)**
In this step, we perform an initial exploration of the dataset. We examine the shape of the data, check for missing values, and generate a statistical summary. This helps in understanding the basic structure of the dataset. We also detect outliers using visualization techniques like boxplots and the Interquartile Range (IQR) method. Any outliers detected are handled appropriately to ensure they do not affect the model's performance.

---

## **Step 4: Feature Engineering**
This step focuses on transforming the data into a format suitable for machine learning models. We perform **Label Encoding** on categorical features, such as `Status`, `Drug`, `Sex`, etc., converting them into numerical values. Additionally, we analyze the target column (`Status`) for potential class imbalance, which is crucial for model performance.

---

## **Step 5: Feature Selection**
Here, we analyze the correlation between different features using a correlation matrix. This allows us to identify any redundant features and avoid multicollinearity, which could negatively impact the performance of the model. We also calculate the **Variance Inflation Factor (VIF)** to further check for multicollinearity among features.

---

## **Step 6: Model Training**
In this step, we split the dataset into training and testing sets. We train two machine learning models to predict the liver cirrhosis stage:

1. **Logistic Regression**: We train and evaluate a Logistic Regression model to see how it performs on both the training and testing sets. We evaluate it using metrics such as accuracy, precision, recall, and confusion matrix.

2. **Random Forest**: We also train a **Random Forest Classifier**, which performs better in capturing complex relationships in the data. After training the model, we evaluate its performance on both the training and testing sets. We also tune the hyperparameters using **RandomizedSearchCV** to further improve the model's performance.

---

## **Step 7: Model Saving and Prediction**
Once the model is trained and evaluated, we save it using **joblib** or **pickle** for future use. This saved model can be loaded later to make predictions on new data without retraining. For demonstration, the saved model is used to make predictions for the first few records in the dataset.

---

## **Conclusion**
The **Random Forest model** outperformed the **Logistic Regression model**, achieving better performance on both training and testing sets. The reason for this is that Random Forest is capable of handling complex, non-linear relationships in the data and is more robust against overfitting.

### **Performance Metrics**:
- **Accuracy**: 93.98% (Training), 91.99% (Testing)
- **Precision**: 94.10% (Training), 92.07% (Testing)
- **Recall**: 93.98% (Training), 91.98% (Testing)

The Random Forest model was selected as the final model due to its superior performance, particularly after hyperparameter tuning. The model demonstrated strong accuracy, precision, and recall, making it ideal for predicting liver cirrhosis stages.

---

### **Visualizations and Insights**:
Throughout the project, various visualizations such as **correlation heatmaps**, **boxplots** for outlier detection, and **confusion matrices** were used to gain deeper insights into the data and evaluate the model's performance effectively.

---

### **Future Work**:
There are opportunities for further improving the model by exploring other advanced techniques, such as:
- **Hyperparameter optimization** with more complex methods like **Grid Search**.
- **Deep learning** models for more advanced prediction.
- **Handling class imbalance** more effectively using techniques like **SMOTE** or **ADASYN**.

---
