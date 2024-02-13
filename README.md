# telecom
Business Problem:
In the telecom industry, customers are able to choose from multiple service providers and actively switch from one operator to another. In this highly competitive market, the telecommunications industry experiences an average of 15-25% annual churn rate. Given the fact that it costs 5-10 times more to acquire a new customer than to retain an existing one, customer retention has now become even more important than customer acquisition. For many incumbent operators, retaining high profitable customers is the number one business goal. To reduce customer churn, telecom companies need to predict which customers are at high risk of churn. In this project, you will analyse customer-level data of a leading telecom firm, build predictive models to identify customers at high risk of churn and identify the main indicators of churn.

Understanding the Business Objective and the Data
The dataset contains customer-level information for a span of four consecutive months - June, July, August and September. The months are encoded as 6, 7, 8 and 9, respectively.

The business objective is to predict the churn in the last (i.e. the ninth) month using the data (features) from the first three months. To do this task well, understanding the typical customer behaviour during churn will be helpful.

Data Dictionary:
The data dictionary contains meanings of abbreviations. Some frequent ones are loc (local), IC (incoming), OG (outgoing), T2T (telecom operator to telecom operator), T2O (telecom operator to another operator), RECH (recharge) etc. The attributes containing 6, 7, 8, 9 as suffixes imply that those correspond to the months 6, 7, 8, 9 respectively.

image

Data Preparation:
Derive new features- This is one of the most important parts of data preparation since good features are often the differentiators between good and bad models. Use your business understanding to derive features you think could be important indicators of churn.

Filter high-value customers- As mentioned above, you need to predict churn only for the high-value customers. Define high-value customers as follows: Those who have recharged with an amount more than or equal to X, where X is the 70th percentile of the average recharge amount in the first two months (the good phase).

Tag churners and remove attributes of the churn phase- Now tag the churned customers (churn=1, else 0) based on the fourth month as follows: Those who have not made any calls (either incoming or outgoing) AND have not used mobile internet even once in the churn phase. The attributes you need to use to tag churners are:

total_ic_mou_9

total_og_mou_9

vol_2g_mb_9

vol_3g_mb_9

After tagging churners, remove all the attributes corresponding to the churn phase (all attributes having ‘ _9’, etc. in their names).

Steps:
* Data Reading & Understanding
* Data Cleaning
* EDA
* Train and Split
* PCA 
* Data Modelling
EDA:
image image image

Models Used:
Logistic Regression
SVM
Random Forest
Decision Tree
Conclusion:
The telecom industry experiences an annual churn rate of 15-25%, making customer retention more important than customer acquisition due to the high cost of acquiring new customers.

To manage High Value Customer Churn, we predicted customers likely to churn and identified factors influencing high churn.

A considerable drop in recharge, call usage, and data usage in the 8th month (Action Phase) was observed during exploratory analysis. Important predictors affecting churn include 'arpu_7', 'max_rech_amt_6', 'std_og_t2m_mou_8', 'loc_og_t2m_mou_8', 'max_rech_data_8', 'last_day_rch_amt_8', 'total_data_rech_8', 'total_amt_8', 'roam_og_mou_8', 'loc_ic_t2m_mou_8'.

The average revenue per user in the 7th month plays a vital role in predicting churn.

Local and STD minutes of usage (incoming and outgoing) are the most influential features on customer churn.

The last day of recharge amount in the action phase and the maximum recharge for calling data in the 6th and 8th months should be focused on to prevent churn.

The last day of recharge, total recharge for data done, and the total amount spent on calls and data in the 8th month also play a crucial role in indicating churn.

Outgoing roaming calls made by clients in the 8th month also play a key role in predicting churn.

Strategies to prevent churn include improving network and customer satisfaction, providing customized plans, routine feedback calls, introducing attractive offers, and promotional offers

Requirements:
matplotlib==3.4.3
numpy==1.20.3
pandas==1.3.4
seaborn==0.11.2
session_info==1.0.0
sklearn==0.24.2
