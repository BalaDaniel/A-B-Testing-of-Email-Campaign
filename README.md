**A/B Testing Analysis – Email Campaign Experiment**
Project Overview

This project analyzes an A/B test experiment for an email marketing campaign. The goal of the experiment is to determine whether Email Variant B performs better than Email Variant A in generating purchases.

Using statistical hypothesis testing, we compare the conversion rates between the two variants and determine whether the observed difference is statistically significant.

**Business Problem**

A company launched two versions of a marketing email:

Variant A – Existing email template

Variant B – New email template

The company wants to know:

Does the new email (Variant B) significantly increase purchase conversion rate compared to Variant A?

**Dataset**

The dataset contains user-level email campaign data with the following columns:

Column	Description
User_ID	Unique identifier for each user
Variant	Email variant (A or B)
Emails_Sent	Whether email was sent
Emails_Opened	Whether email was opened
Link_Clicked	Whether link was clicked
Purchased	Whether user made a purchase
Revenue	Revenue generated from purchase

The dataset contains 5000 observations representing users who received one of the two email variants.

Analysis Steps
1. Data Aggregation

Using Python (Pandas), the data was grouped by variant to calculate key metrics:

Total emails sent

Total emails opened

Total link clicks

Total purchases

Total revenue

Example aggregation:

email_campaign_dataset.groupby("Variant").agg(...)
2. Conversion Metrics Calculation

The following conversion metrics were calculated:

Email Open Rate

Emails Opened / Emails Sent

Click Through Rate

Link Clicked / Emails Opened

Click to Purchase Rate

Purchases / Link Clicked

Email to Purchase Conversion Rate

Purchases / Emails Sent

These metrics help evaluate user behavior at different stages of the email funnel.

3. Hypothesis Testing

To determine if Variant B performs better than Variant A, a two-proportion Z-test was conducted.

Null Hypothesis (H₀)
Conversion rate of Variant A = Conversion rate of Variant B
Alternative Hypothesis (H₁)
Conversion rate of Variant B > Conversion rate of Variant A

Significance level:

α = 0.05

Test statistic formula:

Z = (pB − pA) / SE

Where:

SE = sqrt( p(1−p) (1/nA + 1/nB) )

and p is the pooled proportion.

4. Results
Metric	Variant A	Variant B
Conversion Rate	0.002551	0.004902

Calculated values:

Z statistic ≈ -0.54
p-value > 0.05
5. Conclusion

Although Variant B shows a higher conversion rate than Variant A, the statistical test result indicates that the difference is not statistically significant at the 5% significance level.

Therefore:

Fail to reject the null hypothesis

This means that the observed difference could be due to random variation, and there is insufficient statistical evidence to conclude that Variant B performs better.

**Tools Used**

Python

Pandas

NumPy

SciPy

Jupyter Notebook

GitHub

Key Learnings

Implemented A/B testing using statistical hypothesis testing

Calculated conversion funnel metrics

Applied two-proportion Z-test

Interpreted statistical results for business decision making

Future Improvements

Possible extensions of this project:

Visualizing conversion funnel

Running statistical power analysis

Performing Bayesian A/B testing

Analyzing revenue impact of each variant
