# EXL-Term-Depositor-Analysis
---------------------------------------------

 This project was made as part of the [EXL EQ 2022](http://www.exlanalytics.co.in/eq/frontend/web/) contest.

# Team Members
----------------------------------------------------

  * [@Vikas](https://github.com/Vikasz2201)
  * [@Lakshay Kapoor](https://github.com/techmaxus)

# Problem Statement
-----------------------------------------------------------------------

In 2018, the firm launched a new investment product, “Term Deposit”, which has observed a rapid growth since its inception. The increase in term deposit accounts has provided the firm with additional funds to create other offerings. Hence, based on this performance, it further wants to increase its term deposit accounts amongst existing customers. In order to do so, the firm plans to run a campaign and wants EXL to identify a list of customers who could be contacted via telecommunication channels to open a term deposit account with ABC. Since the campaign will be run for a short period of time, and owing to budget constraints, the firm wants a list of only 1000 customers from EXL for the target list.

# Solution
--------------------------------------------------------------------------

  Our solution covers five main aspects-

  * The original data set with top 8 feature based on information gain was used with Random forest to provide a list of 745 potential term depositor.
  * Common feature such as  housing loan and personal loan were combined to make a new feature "having loan". This updated dataset was used to derive result using various model to provide list of 343 potential term depositor.
  * Data was oversampled using random sampling method and subjected to Random forest to yield a list of 677 potential term depositor.
  * These three results were combined by taking a union to provide a exhaustive list of 947 customer.
  * The remaining 53 entries were aggregated by applying Adaboost on under sampled data using Near-Miss method to finalise the result.

# Analysis Approach
--------------------------------------------------------------------------------------------

The historical data provided to us contains a list of ABC customers, who were approached to open a term deposit account with ABC in past campaigns. This data was having 23880 data points and 16 features and 1 decision variable. We also received a list of new customer which contained list of new customer with same feature set and without decision variable.

On analysing the training data the significant correlation was found with 8 features only. We calculated precision, recall, accuracy and F1 score for various models and Random Forest was calculated as most suitable model. After tuning its hyperparameter 745 positive results(potential term depositor from campaign).

Some feature such as having housing loan or having personal loan can be clubbed together to provide a better result outcome. On calculating metrics such as accuracy, recall, precision and 3 models (Adaboost, XGBoost and decision tree) were found suitable for this dataset. After tuning hyperparameters of these models and taking thier union 343 term depositor were predicted as positive.

The data provided is highly skewed towards single decision variable outcome. Hence oversampling using random sampling was done to provide a larger dataset. The metrics on new data suggested for Random forest Classifier for best result. On training and tuning  the model on new dataset it yeilded a positive result for 677 data points. Using undersampling by near miss method , the metrics suggested to use adaboost model which even after hyperparameter tuning gave 5418 possitive results. So previously trained model were applied on positive data points to decrease number of positive test results to 548.

The union of top 8 feature model, combined feature model, oversampled model accounted 947 data entries. Since top 1000 entries wer needed to be submitted 53 top entries were taken from under sampled data.

# Conclusion
-------------------------------------------------------------------------------------------
  Top most important feature were :
  * customer_age
  * job_type
  * balance
  * housing_loan
  * last_contact_duration
  * prev_compaign_outcome
  * day_of_month
  * month

  <b>We further divided these factor into 2 buckets:</b>
  * <b>User Profile</b>
    * customer_age
    * job_type
    * balance
    * housing_loan
    * last_contact_duration
    * prev_compaign_outcome
  * <b>Campaign profile</b>
    * day_of_month
    * month

  <h2><b>Goal</b></h2>
  To find top 1000 users who are likely to open a term deposit account given their profile and date and month at which they will be approached.

  <h2><b>Further Goal</b></h2>
  To have high conversion rate in the campaign we need to increase positive outcome probability by tuning the campaign parameter such as date and month for given user profile.


