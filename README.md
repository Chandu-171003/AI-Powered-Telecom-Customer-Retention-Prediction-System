<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Customer Churn Prediction System</title>
</head>
<body>

<h1>📊 Customer Churn Prediction System</h1>

<p>
An end-to-end telecom churn prediction system combining exploratory data analysis,
feature engineering, machine learning, and Flask deployment to predict customer churn
and support customer retention strategies.
</p>

<hr>

<!-- ================= VISUALIZATIONS ================= -->

<h2>📈 Exploratory Data Analysis & Model Visualizations</h2>

<p>
The project includes comprehensive visual analysis to understand customer behavior,
churn drivers, and model performance.
</p>

<h3>EDA Visual Insights</h3>
<ul>
  <li>Customer churn distribution</li>
  <li>Tenure and contract-based churn patterns</li>
  <li>Payment methods and billing behavior</li>
  <li>Service usage, add-ons, and bundling impact</li>
  <li>Demographic, SIM-wise, and senior citizen analysis</li>
</ul>

<p>
All EDA plots are available in <strong>CRPS-Documentation.pdf</strong>.
</p>

<hr>

<h3>📊 Model Performance & ROC Analysis</h3>

<p>
Multiple machine learning models were evaluated using Test Accuracy and AUC scores.
ROC curves were generated to visually compare model discrimination ability.
</p>

<table border="1" cellpadding="8" cellspacing="0">
  <tr>
    <th>Algorithm</th>
    <th>Test Accuracy</th>
    <th>AUC Score</th>
  </tr>
  <tr><td>KNN</td><td>0.7232</td><td>0.7248</td></tr>
  <tr><td>Naive Bayes</td><td>0.7935</td><td>0.8366</td></tr>
  <tr><td>Logistic Regression</td><td>0.7260</td><td>0.8103</td></tr>
  <tr><td>Decision Tree</td><td>0.6962</td><td>0.6425</td></tr>
  <tr><td>Random Forest</td><td>0.7480</td><td>0.6519</td></tr>
  <tr><td>AdaBoost</td><td>0.7821</td><td>0.8094</td></tr>
  <tr><td>Gradient Boosting</td><td>0.7296</td><td>0.8302</td></tr>
  <tr><td>XGBoost</td><td>0.7594</td><td>0.8276</td></tr>
  <tr><td>SVM</td><td>0.7353</td><td>0.7320</td></tr>
</table>

<p>
ROC curves for all models are available in <strong>AUC_ROC_Curve.pdf</strong>.
Naive Bayes, Gradient Boosting, and XGBoost demonstrated strong AUC performance.
</p>

<hr>

<!-- ================= WORKFLOW ================= -->

<h2>🔁 Project Workflow</h2>
<ol>
  <li>Data loading and cleaning</li>
  <li>Missing value imputation</li>
  <li>Outlier treatment and variable transformation</li>
  <li>Feature selection</li>
  <li>Categorical encoding</li>
  <li>Class imbalance handling using SMOTE</li>
  <li>Model training and evaluation</li>
  <li>ROC–AUC comparison</li>
  <li>Model serialization</li>
  <li>Flask-based deployment</li>
</ol>

<hr>

<!-- ================= FILE STRUCTURE ================= -->

<h2>📁 File Descriptions</h2>

<h3>main.py</h3>
<p>
Acts as the core pipeline controller. Loads data, performs preprocessing,
feature engineering, encoding, class balancing, and triggers model training.
</p>

<h3>random_sample_imputation.py</h3>
<p>
Handles missing values using random sample imputation to preserve data distribution.
</p>

<h3>var_trnsf_outlrs.py</h3>
<p>
Applies Yeo-Johnson transformation and IQR-based trimming for outlier handling.
</p>

<h3>feature_selection.py</h3>
<p>
Removes constant and quasi-constant features and applies correlation-based selection.
</p>

<h3>imbalance_data.py</h3>
<p>
Uses SMOTE for class balancing and applies feature scaling. Saves the scaler.
</p>

<h3>all_models.py</h3>
<p>
Trains and evaluates multiple ML models, generates ROC curves, logs metrics,
and saves the best-performing model.
</p>

<h3>app.py</h3>
<p>
Flask web application for real-time customer churn prediction.
</p>

<h3>log_code.py</h3>
<p>
Centralized logging utility used across all modules for debugging and monitoring.
</p>

<h3>CRPS-Documentation.pdf</h3>
<p>
Contains all EDA visualizations and business insights.
</p>

<h3>AUC_ROC_Curve.pdf</h3>
<p>
Includes ROC curves and AUC scores for all trained models.
</p>

<hr>

<h2>🎯 Key Results</h2>
<ul>
  <li>High churn observed in early tenure and month-to-month contracts</li>
  <li>Bundled services and long-term contracts improve retention</li>
  <li>Ensemble models achieved strong ROC-AUC scores</li>
  <li>End-to-end pipeline supports real-time churn prediction</li>
</ul>

<hr>

<h2>🚀 Future Enhancements</h2>
<ul>
  <li>Hyperparameter tuning</li>
  <li>Automated ML pipelines</li>
  <li>Cloud deployment</li>
  <li>Real-time dashboards</li>
  <li>Model monitoring and retraining</li>
</ul>

<hr>

<p><strong>Author:</strong> Chandra Kanth</p>
<p><strong>Domain:</strong> Machine Learning | Data Science | Telecom Analytics</p>

</body>
</html>
