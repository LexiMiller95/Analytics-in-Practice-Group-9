# Analytics-in-Practice-Group-9

**Roles of each group member:**

  Rathesh - Data Engineer

  Chaitanya - Data Engineer

  Ayce - Modeler/Analyst

  Anh - Modeler/Analyst

  Ahmad - LLM/Prompt Specialist

  Avirall - Visualization Expert

  Iliana - Visualization Expert

  Nisa - Project Manager/Storyteller

  Lexi - Project Manager/Storyteller

---

## how-to-run:

**Download Ecommerce Churn Dataset 2025.csv as it is the core csv file used in this project; can also be found on kaggle.com**

1. EDA_Data_Cleaning_and_Feature_Engineering - This notebook handles the initial data cleaning, feature engineering, and relevant EDA that would complement and be relevant to the problem statements applied on the cleaned data. In addition, there are brief notes, interpretations, and key findings in each section so it’s easy to follow and useful for next steps like model building and visualization. Run everything in order as pipeline dependencies exist. If errors occur: Check data paths & ensure all libraries are installed. For best results do not modify preprocessing without understanding impact.

2. MAIN_Churn_Prediction_and_Customer_Analytics - End-to-end customer churn analysis and machine learning pipeline that transforms raw data into actionable retention strategies. This is the primary model used for our project as it was determined to be most accurate. Run everything in order as pipeline dependencies exist. If errors occur: Check data paths & ensure all libraries are installed. For best results do not modify preprocessing without understanding impact.

ARCHIVED_Churn_Prediction_and_Customer_Analytics - A separate model that was determined to be less accurate than the MAIN model. Including for record keeping, but not recommended to run as part of the project.

3. Customer_Segmentation_RFM_Analysis - Customer segmentation using RFM analysis to identify high-value and at-risk customers for targeted business strategies. Run everything in order as pipeline dependencies exist. If errors occur: Check data paths & ensure all libraries are installed. For best results do not modify preprocessing without understanding impact.

**Model_Report_-_Ecommerce_Customer_Analytics.docx.pdf - pdf report of model performance, findings, and limitations 

**Additional visualizations can be found in the following Tableau dashboard https://public.tableau.com/app/profile/avirall8075/viz/AIP2_1/E-CommerceChurnOverview

---

## AI Usage Summary

This project incorporated AI tools (including Claude and Copilot) to support EDA, feature engineering, and model development. 

1. Exploratory Data Analysis (EDA)

Initial Prompt:
"Given this ecommerce customer dataset, outline a comprehensive EDA approach. Include data cleaning steps, handling missing values, detecting outliers, and key visualizations relevant to churn prediction."

Output Summary:
The AI generated a structured EDA workflow that included:
* Data cleaning steps (handling nulls, removing duplicates)
* Suggested imputation strategies (mean/median/mode depending on feature type)
* Outlier detection methods (IQR, z-score)
* Feature distributions and correlation analysis
* Visualizations such as histograms, boxplots, and heatmaps
* Initial hypotheses about churn drivers (e.g., low purchase frequency, high recency)

Evaluation of Output:
The output was well-structured and provided a strong general framework. However:
* It was somewhat generic 
* Limited prioritization of which features were most relevant to churn
* Lacked direct linkage between EDA findings and downstream modeling decisions

---

2. Feature Engineering

Initial Prompt:
"Using the results of our EDA on an ecommerce dataset, suggest advanced feature engineering techniques specifically for churn prediction. Consider temporal behavior, customer value metrics, and interaction effects between variables."

Output Summary:
The AI proposed:
* RFM (Recency, Frequency, Monetary) feature construction
* Customer lifetime value approximations
* Time-based features (e.g., days since last purchase)
* Aggregated behavioral metrics (average order value, purchase intervals)
* Interaction features (e.g., frequency × monetary value)
* Binning strategies for segmentation

Evaluation of Output:
The suggestions were highly relevant and aligned with industry practices:
* Strong emphasis on business-relevant features (RFM, CLV)
* Useful ideas for temporal and behavioral aggregation

Limitations:
* Some features were redundant or highly correlated
* No clear prioritization or feature selection strategy
* Limited guidance on scaling or encoding for model compatibility

Refinement Prompt:
"From the proposed feature set, identify the most impactful features for churn prediction and explain why. Recommend feature selection techniques and address potential multicollinearity and scaling requirements for machine learning models."

---

3. Model Development

Initial Prompt:
"Given a cleaned and feature-engineered ecommerce dataset for churn prediction, recommend suitable machine learning models. Include justification, expected performance trade-offs, and guidance on evaluation metrics."

Output Summary:
The AI recommended:
* Logistic Regression (baseline, interpretable)
* Random Forest (robust to non-linearity, feature importance)
* Gradient Boosting (e.g., XGBoost, high performance)
* Evaluation metrics such as accuracy, precision, recall, F1-score, and ROC-AUC
* Cross-validation for model stability

Evaluation of Output:
The recommendations were appropriate and aligned with standard practice:
* Good balance between interpretability and performance
* Correct emphasis on classification metrics

Limitations:
* Did not initially prioritize recall/precision trade-offs for churn use case
* Lacked implementation-level detail (hyperparameter tuning, pipelines)
* Minimal discussion of class imbalance handling

Refinement Prompt:
"For a churn prediction problem where identifying at-risk customers is critical, refine the model selection and evaluation approach. Emphasize handling class imbalance, optimizing recall, and suggest specific hyperparameter tuning strategies."

---

## 4. Code Generation Support (Copilot)

Sample Prompt:
"Generate Python code for implementing a churn prediction pipeline, including preprocessing, feature engineering, model training, and evaluation."

Output Summary:
Copilot assisted with:
* Data preprocessing pipelines (scaling, encoding)
* Model implementation (e.g., Random Forest, Gradient Boosting)
* Train-test split and evaluation metrics
* SMOTE dataset balancing 
* Basic feature importance extraction

Evaluation of Output:
* Accelerated development and reduced boilerplate coding
* Generally correct syntax and structure

Limitations:
* Required manual validation and debugging
* Occasionally produced inefficient or redundant code
* Limited contextual understanding of dataset-specific nuances

---

## Overall Assessment

AI tools significantly improved productivity and ideation by:

* Providing structured approaches to EDA and modeling
* Suggesting industry-relevant feature engineering techniques
* Accelerating code generation and implementation

However, effective use required:

* Iterative prompting to refine generic outputs
* Critical evaluation of suggestions
* Manual validation and domain-specific adjustments

The combination of AI-generated insights and human oversight resulted in a more robust and accurate churn prediction pipeline.
