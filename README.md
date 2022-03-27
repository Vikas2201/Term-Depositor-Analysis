# EXL-Term-Depositor-Analysis
---------------------------------------------

 This project was made as part of the EXL EQ 2022 contest.

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

