<h1 align="center">AI Powered Telecom Customer Retention Prediction System</h1>

<p align="center">
<b>Major Project Report | Data Science & Machine Learning | Telecom Analytics</b>
</p>

<hr/>

<h2>📌 Project Overview</h2>
<p>
Customer churn prediction is a critical analytical problem in the telecom industry, where
organizations aim to identify customers who are likely to discontinue services.
This project implements an end-to-end machine learning pipeline to analyze customer
behavior, predict churn probability, and support proactive retention strategies.
</p>

<p>
The system integrates data preprocessing, exploratory analysis, feature engineering,
statistical feature selection, machine learning model training, evaluation, and deployment
using a Flask-based web application.
</p>

<hr/>

<h2>🏗 System Architecture</h2>
<p>
The overall system architecture follows a structured machine learning workflow to ensure
data quality, reliable predictions, and real-world deployment readiness.
</p>

<ol>
  <li>Data Cleaning & Preprocessing</li>
  <li>Exploratory Data Analysis (EDA)</li>
  <li>Feature Engineering</li>
  <li>Feature Selection</li>
  <li>Train–Validation–Test Split</li>
  <li>Model Training (Multiple ML Models)</li>
  <li>Model Evaluation & Comparison</li>
  <li>Hyperparameter Tuning</li>
  <li>Final Model Selection</li>
  <li>Model Serialization (Pickle / Joblib)</li>
  <li>API Development (Flask)</li>
  <li>Deployment & Monitoring</li>
</ol>

<hr/>

<h2>📝 Abstract</h2>
<p>
This project focuses on predicting telecom customer churn by analyzing demographic,
service usage, and billing-related attributes. Comprehensive preprocessing techniques
including missing value handling, encoding, scaling, and class imbalance treatment were
applied to ensure high-quality inputs.
</p>

<p>
Exploratory Data Analysis (EDA) revealed key churn drivers such as contract type, tenure,
payment method, and service add-ons. Multiple machine learning models were trained and
evaluated using accuracy, precision, recall, F1-score, and ROC–AUC metrics.
</p>

<p>
The final deployed system enables organizations to identify high-risk customers in advance
and implement targeted retention strategies.
</p>

<hr/>

<h2>📘 Introduction</h2>
<p>
Customer churn prediction is a supervised machine learning problem where the target
variable indicates whether a customer will leave the service. The dataset contains both
numerical and categorical features representing customer demographics, subscriptions,
usage behavior, and billing information.
</p>

<p>
Since machine learning algorithms operate on numerical data, extensive preprocessing
steps such as encoding, scaling, and missing value treatment were applied. Class imbalance
was addressed to ensure robust model learning.
</p>

<p>
Multiple models including Logistic Regression, Random Forest, XGBoost, and Naive Bayes
were evaluated using ROC–AUC as the primary selection metric.
</p>

<hr/>

<h2>🧰 Requirements for Model Development</h2>
<ul>
  <li>Flask – Web framework for backend development</li>
  <li>Gunicorn – Production WSGI server</li>
  <li>NumPy – Numerical computation</li>
  <li>Pandas – Data manipulation</li>
  <li>Matplotlib – Visualization</li>
  <li>Seaborn – Statistical visualization</li>
  <li>Scikit-learn – ML algorithms and preprocessing</li>
  <li>Imbalanced-learn – SMOTE for class balancing</li>
  <li>Statsmodels – Statistical testing</li>
  <li>Feature-engine – Feature transformations</li>
  <li>Joblib / Pickle – Model serialization</li>
</ul>

<hr/>

<h2>📊 Data Visualization (EDA)</h2>

<h3>Visualization Overview</h3>
<p>
Matplotlib and Seaborn libraries were used to visualize customer behavior and churn
patterns. Bar charts, pie charts, count plots, box plots, and histograms were employed.
</p>

<h3>Customer Churn Distribution</h3>
<p>
A bar chart comparing churned vs retained customers shows that although most customers
are retained, even a small churn percentage can lead to significant revenue loss.
</p>

<h3>Gender-wise Churn Analysis</h3>
<p>
Male and female churn distributions indicate similar retention patterns, showing that
gender alone is not a strong churn predictor.
</p>

<h3>Payment Method Distribution</h3>
<p>
Electronic check users form the largest group and are often associated with higher churn,
while automatic payment users exhibit better retention.
</p>

<h3>Contract Type Analysis</h3>
<p>
Month-to-month contracts dominate the dataset and show higher churn. Long-term contracts
strongly improve customer retention.
</p>

<h3>Paperless Billing</h3>
<p>
Most customers prefer paperless billing. Digitally engaged customers tend to stay longer.
</p>

<h3>Streaming & Add-on Services</h3>
<p>
Customers with multiple add-on services such as streaming, security, and tech support
show lower churn due to higher engagement.
</p>

<h3>Internet Service & Multiple Lines</h3>
<p>
Fiber optic users generally show lower churn. Customers with multiple lines are more
invested and less likely to churn.
</p>

<h3>Partner, Dependents & Senior Citizens</h3>
<p>
Customers with partners and dependents churn less. Senior citizens form a smaller group
but require targeted plans.
</p>

<h3>Final EDA Observations</h3>
<p>
Tenure, contract type, payment method, and billing type are the most influential churn
drivers. Early-stage customers show the highest churn risk.
</p>

<hr/>

<h2>🛠 Feature Engineering</h2>

<h3>Handling Missing Values</h3>
<p>
Several imputation techniques were evaluated:
</p>
<ul>
  <li>Random Sample Imputation – Preserves distribution but increased variance</li>
  <li>Mean / Median / Mode Imputation – Alters standard deviation</li>
  <li>Dropping Missing Data – Risk of data loss</li>
  <li>Constant / Arbitrary / End of Distribution – Introduces artificial bias</li>
</ul>

<p>
Based on evaluation, the most suitable approach was selected to maintain data stability.
</p>

<h3>Data Separation</h3>
<p>
Features were separated into numerical and categorical variables to apply appropriate
preprocessing techniques.
</p>

<h3>Variable Transformation</h3>

<h4>Power Transformation</h4>
<p>
Applied to reduce skewness but failed to achieve normality.
</p>

<h4>Arcsin Transformation</h4>
<p>
Applicable only to proportional data; not suitable for this dataset.
</p>

<h4>Log Transformation</h4>
<p>
Failed to significantly improve distribution.
</p>

<h4>Box-Cox Transformation</h4>
<p>
Restricted to positive values and did not yield sufficient improvement.
</p>

<h4>Yeo–Johnson Transformation (Best)</h4>
<p>
Handled both positive and negative values and improved feature normality, making it the
preferred transformation.
</p>

<h3>Handling Outliers</h3>

<h4>Capping</h4>
<p>
Simple but not data-driven; risk of information loss.
</p>

<h4>Trimming</h4>
<p>
Removes extreme values but leads to data loss; not selected.
</p>

<h4>5th–95th Quantile Method</h4>
<p>
Caps extreme values while preserving data; used in preprocessing.
</p>

<hr/>

<h2>🎯 Feature Selection</h2>

<h3>Categorical Encoding</h3>
<ul>
  <li>One-Hot Encoding – Nominal variables</li>
  <li>Ordinal Encoding – Contract type</li>
  <li>Label Encoding – Target variable</li>
</ul>

<h3>Filter Methods</h3>

<h4>Constant & Quasi-Constant Features</h4>
<p>
Variance thresholding was applied; no features were removed.
</p>

<h3>Hypothesis Testing</h3>

<h4>ANOVA Test</h4>
<p>
Used for numerical vs categorical feature relationships.
</p>

<h4>Chi-Square Test (Best)</h4>
<p>
Used to select statistically significant categorical features.
</p>

<h4>Correlation Analysis</h4>
<p>
Used to detect multicollinearity among numerical features.
</p>

<hr/>

<h2>⚖️ Data Balancing</h2>
<p>
SMOTE (Synthetic Minority Over-sampling Technique) was applied to handle class imbalance
by generating synthetic minority class samples.
</p>

<hr/>

<h2>📏 Feature Scaling</h2>
<p>
Standard Scaling (Z-score normalization) was applied to numerical features to ensure
uniform scale across inputs.
</p>

<hr/>

<h2>🤖 Model Training & Evaluation</h2>
<p>
Multiple classification models were trained. Performance was evaluated using ROC and AUC
metrics to ensure threshold-independent comparison.
</p>

<h3>ROC & AUC</h3>
<p>
ROC curves visualize sensitivity vs specificity trade-offs. AUC represents the model’s
overall discriminative power.
</p>

<hr/>

<h2>🏆 Best Model</h2>
<p>
The Naive Bayes classifier achieved the highest ROC–AUC score (~0.836) and demonstrated
stable performance. The trained model was serialized using Pickle for deployment.
</p>

<hr/>

<h2>🌐 Frontend & Backend</h2>
<p>
A Flask-based web application was developed. Users input customer details via an HTML
form, and real-time churn prediction with probability is displayed on the same page.
</p>

<hr/>

<h2>📈 Results</h2>
<p>
The deployed system successfully predicts customer churn and supports proactive
retention decision-making.
</p>

<hr/>

<h2>📌 Conclusion</h2>
<p>
This project demonstrates how machine learning can be effectively applied to customer
retention problems. By combining robust preprocessing, statistical analysis, and
deployment, the system delivers actionable churn predictions.
</p>

<hr/>

<h2>🚀 Future Enhancements</h2>
<ul>
  <li>Deep Learning models (ANN, CNN, LSTM)</li>
  <li>Real-time streaming data pipelines</li>
  <li>Interactive analytics dashboard</li>
  <li>Scalable cloud deployment</li>
</ul>

<hr/>

<h2>🧑‍💻 Author</h2>
<p>
<b>M. Chandra Kanth</b><br/>
Data Science Intern<br/>
The Skill Union | Vihara Tech | 
Contact Mail : mck42945@gmail.com
</p>

<hr/>

<h2>📚 References</h2>
<ul>
  <li>Kaggle – Telco Customer Churn Dataset</li>
  <li>Scikit-learn Documentation</li>
  <li>Pandas & NumPy Documentation</li>
  <li>Flask Official Documentation</li>
</ul>
