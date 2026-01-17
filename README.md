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
Exploratory Data Analysis (EDA) was performed to understand customer behavior,
identify churn patterns, and discover key business drivers influencing customer retention.
</p>

<h3>EDA Visual Insights</h3>

<ul>
  <li>
    <strong>Customer Churn Distribution:</strong>
    Shows the proportion of customers who churned versus those retained, highlighting
    the presence of class imbalance and the overall churn problem.
  </li>

  <li>
    <strong>Tenure & Contract-Based Analysis:</strong>
    Visualizes how churn is higher during early customer tenure and among month-to-month
    contract users, indicating the importance of early-stage retention strategies.
  </li>

  <li>
    <strong>Payment Methods & Billing Behavior:</strong>
    Demonstrates that customers using manual payment methods and non-paperless billing
    exhibit higher churn compared to customers using automatic payment options.
  </li>

  <li>
    <strong>Service Usage & Add-on Analysis:</strong>
    Shows that customers subscribing to multiple services such as streaming, security,
    and technical support tend to remain longer, proving the value of service bundling.
  </li>

  <li>
    <strong>Demographic & SIM-wise Analysis:</strong>
    Analyzes churn patterns across gender, senior citizens, dependents, and SIM providers,
    revealing that family-oriented customers are generally more stable.
  </li>
</ul>

<p>
All EDA visualizations and insights are documented in <strong>CRPS-Documentation.pdf</strong>.
</p>

<hr>

<!-- ================= AUC ROC ================= -->

<h3>📊 Model Performance & AUC–ROC Analysis</h3>

<p>
Multiple machine learning models were trained and evaluated using Test Accuracy and
AUC (Area Under the ROC Curve). AUC–ROC is preferred for churn prediction because it
measures a model’s ability to distinguish between churn and non-churn customers,
even when the dataset is imbalanced.
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
Models with higher AUC values demonstrate better separation between churned and
retained customers.
</p>

<hr>
<h3>Architecture Flow Explanation</h3>
<ol>
  <li>
    <strong>Data Source:</strong> Telecom customer data containing demographics,
    services, billing, tenure, and churn information.
  </li>
  <li>
    <strong>Data Preprocessing:</strong> Missing value imputation, outlier treatment,
    variable transformation, and feature selection to clean and optimize the dataset.
  </li>
  <li>
    <strong>Feature Engineering:</strong> Categorical encoding, numerical scaling,
    and feature reduction to prepare data for modeling.
  </li>
  <li>
    <strong>Class Imbalance Handling:</strong> SMOTE is applied to balance churn
    and non-churn classes.
  </li>
  <li>
    <strong>Model Training & Evaluation:</strong> Multiple ML models are trained
    and evaluated using Accuracy and AUC–ROC metrics.
  </li>
  <li>
    <strong>Best Model Selection:</strong> Naive Bayes is selected based on highest
    AUC score and stable performance.
  </li>
  <li>
    <strong>Model Serialization:</strong> The trained model and scaler are saved
    for deployment.
  </li>
  <li>
    <strong>Flask Deployment:</strong> A web application accepts user input and
    returns real-time churn predictions.
  </li>
</ol>

<!-- ================= BEST MODEL ================= -->

<h3>🏆 Best Model Selection</h3>

<p>
<strong>Naive Bayes</strong> was selected as the final model because it achieved the
<strong>highest AUC score (0.8366)</strong> along with strong test accuracy.
This indicates superior performance in identifying churn-prone customers.
</p>

<p>
Additionally, Naive Bayes is computationally efficient, robust to noise, and performs
well with scaled and transformed features, making it suitable for real-time deployment.
The trained Naive Bayes model was saved and used in the Flask application.
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
  <li>AUC–ROC comparison</li>
  <li>Best model selection</li>
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

<hr>

<h2>🎯 Key Results</h2>
<ul>
  <li>High churn observed in early tenure and month-to-month contracts</li>
  <li>Bundled services and long-term contracts improve retention</li>
  <li>Naive Bayes achieved the best AUC performance</li>
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
</body>
</html>
