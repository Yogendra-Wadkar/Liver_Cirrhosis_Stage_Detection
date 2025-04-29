<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Liver Cirrhosis Stage Prediction</title>
</head>
<body>
    <h1>Liver Cirrhosis Stage Prediction</h1>
    <p>This project aims to predict the stage of liver cirrhosis using a dataset containing various medical features. Several machine learning algorithms were experimented with, and after tuning hyperparameters, Random Forest was chosen as the final model due to its performance in handling complex relationships in the data.</p>

    <h2>Step 1: Import Libraries</h2>
    <p>We begin by importing necessary libraries:</p>
    <ul>
        <li>NumPy, Pandas for data handling</li>
        <li>Matplotlib and Seaborn for data visualization</li>
        <li>Scikit-learn for machine learning models, preprocessing, and evaluation metrics</li>
        <li>Statsmodels for Variance Inflation Factor (VIF) calculation</li>
        <li>Pickle for model saving and loading</li>
    </ul>

    <h2>Step 2: Data Gathering</h2>
    <p>The dataset is read from a CSV file into a DataFrame:</p>
    <pre><code>df = pd.read_csv(r"D:\Jupyter python\New Datasets\Unified Mentor\liver_cirrhosis_stage\liver_cirrhosis.csv")</code></pre>

    <h2>Step 3: Exploratory Data Analysis (EDA)</h2>
    <p>We explore the dataset by checking for null values, data types, and basic statistics:</p>
    <ul>
        <li>Shape of the dataset</li>
        <li>Data types and missing values</li>
        <li>Statistical summary</li>
    </ul>
    <p>Outliers are detected using boxplots and the Interquartile Range (IQR) method. The outliers are replaced with boundary values.</p>

    <h2>Step 4: Feature Engineering</h2>
    <p>We perform label encoding for categorical features to convert them into numerical values:</p>
    <ul>
        <li>Status, Drug, Sex, Ascites, Hepatomegaly, Spiders, and Edema columns are encoded using a dictionary mapping.</li>
    </ul>
    <p>Additionally, we analyze the target column 'Status' which shows imbalance in the dataset.</p>

    <h2>Step 5: Feature Selection</h2>
    <p>We check for feature correlations using Pearson's coefficient and visualize the correlation matrix:</p>
    <ul>
        <li>The correlation matrix is plotted using Seaborn heatmaps.</li>
    </ul>
    <p>Variance Inflation Factor (VIF) is calculated to check for multicollinearity among features.</p>

    <h2>Step 6: Model Training</h2>
    <p>The dataset is split into training and testing sets using <code>train_test_split</code>. Two models are trained:</p>
    <h3>1. Logistic Regression</h3>
    <p>The Logistic Regression model is trained and evaluated on both training and testing sets. Evaluation metrics such as accuracy, confusion matrix, classification report, precision, and recall are calculated.</p>
    
    <h3>2. Random Forest</h3>
    <p>The Random Forest Classifier is trained using the training set. The model is evaluated similarly to Logistic Regression. Precision and recall metrics are recorded. Hyperparameter tuning is done using RandomizedSearchCV, which significantly improves the model's performance.</p>

    <h2>Step 7: Model Saving and Prediction</h2>
    <p>The trained Random Forest model is saved using <code>joblib.dump</code> and can be loaded later for making predictions. Here, we load the saved model and make predictions for the first 5 records in the dataset.</p>

    <h2>Conclusion</h2>
    <p>The Random Forest model with hyperparameter tuning resulted in the best performance with the following metrics:</p>
    <table border="1">
        <tr>
            <th>Metric</th>
            <th>Training (%)</th>
            <th>Testing (%)</th>
        </tr>
        <tr>
            <td>Accuracy</td>
            <td>93.98</td>
            <td>91.99</td>
        </tr>
        <tr>
            <td>Precision</td>
            <td>94.10</td>
            <td>92.07</td>
        </tr>
        <tr>
            <td>Recall</td>
            <td>93.98</td>
            <td>91.98</td>
        </tr>
    </table>
    <p>The reason Random Forest was preferred over Logistic Regression is its ability to capture complex relationships in the data and its robustness against overfitting. Hyperparameter tuning further optimized its performance.</p>
</body>
</html>
