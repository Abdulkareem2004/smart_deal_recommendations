Problem Statement:
Retail companies and online platforms provide discount coupons to customers, but not all coupons are redeemed. The challenge is to predict whether a customer will redeem a coupon or not, based on their personal, travel, and contextual information. This helps businesses improve coupon targeting and marketing strategies.

Approach Followed

1. Data Understanding & Cleaning

Removed unnecessary columns (like Unnamed indices).

Handled categorical and numerical features separately.



2. Exploratory Data Analysis (EDA)

Checked class distribution (redeemed vs not redeemed).

Visualized important features to understand user behavior.



3. Preprocessing

Numerical columns scaled with StandardScaler.

Categorical columns encoded with OneHotEncoder.



4. Model Building & Training
Split data into training (80%) and testing (20%).

Trained three models:

Logistic Regression

Random Forest

XGBoost




5. Evaluation

Used metrics: Accuracy, Precision, Recall, F1-score, ROC-AUC.

Compared models and selected the best performer.   

Split data into training (80%) and testing (20%).

Dataset Used

File: smart_deal_recommendations.csv

Size: ~25 columns, 10k+ rows.

Features:

User details (age, gender, income group, marital status, etc.)

Travel details (travel type, trip purpose, company, direction match, etc.)

Context features (weather, coupon type, validity).


Target Variable:

redeemed (1 = coupon redeemed, 0 = not redeemed).

Model Details

Logistic Regression – baseline linear model.

Random Forest – ensemble tree model (n=200 trees).

XGBoost – gradient boosting model with eval_metric=logloss.

Pipeline:

ColumnTransformer for preprocessing.

Models trained and tested via Pipeline.

Results Achieved

Model	              Accuracy	Precision	Recall	F1-score	ROC-AUC

Logistic Regression	 0.686	   0.701	  0.780	   0.739	   0.671
Random Forest	       0.756	   0.757	  0.840	   0.796	   0.742
XGBoost	             0.745	   0.753	  0.820	   0.785	   0.733


👉 Random Forest performed the best with ~76% accuracy and a good balance of precision & recall.

