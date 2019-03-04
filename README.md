
# Analyze A/B Test Results

## Overview

The objective of this project is to assist a company, after running an A/B test on an e-commerce website,
to decide if they should implement the new page, keep the old page, or perhaps run the experiment longer.

## Install

The following packages are required to run the notebook:
-	Jupyter Notebooks
-	Python
-	pandas (includes numpy)
-	matplotlib


## Source

'ab_data.csv' is provided by the Udacity server, available to be downloaded [at this link](https://d17h27t6h515a5.cloudfront.net/topher/2017/December/5a32c9db_analyzeabtestresults-2/analyzeabtestresults-2.zip).

## Files

|Files|Description|
|---|---|
|Analyze_ab_test_results_notebook.ipynb|Code for the A/B Test|
|Analyze_ab_test_results_notebook.html| Exported version of the notebook|


## A/B Test Results

Per the probabilities calculated in Part I, the results do not show enough evidence that suggest that one page
leads to more conversions. The chance individuals convert from groups control and treatment are pretty even.

By simulating the difference in conversion rates under the null, setting the null hypothesis as the old page
is better than the new page, and the alternative as the opposite (at a type I error rate of 5%), the calculated
p-value (~90.58%) lead to the decision of failing to reject the null. Same decision was achieved through the z-test,
with a z-score of 1.31 (< critical value of 1.96 at 95% confidence) associated to a p-value of 90.51% (very close
to the got one in the simulation). Per both tests, statistically the old version has higher probability to lead to
more conversions than the new one.

By performing the (logistic) regression, the null hypothesis is set as there is no difference in conversion for
both groups, control and treatment; the alternative sets there is difference. The associated p-values to the
coefficients are small (the variables ab_page, UK & US are statistically significant), and the multiplicative
change in conversion is barely more than 1 time, suggesting the country has no impact on the conversion rate
difference (failing to reject the null). By adding the relation between the page and the country, the model does
not show to be a better fit on predicting the conversion response.

Per the results of all these tests, statistically, the company should keep the old page rather than implementing
the new version. However, as the chance of conversion is around 12% (even regardless the group) and the difference
in conversion for both is pretty small (0.16%), in practice, it might be better to invest improving on the new one
in order to rise the conversion rate.