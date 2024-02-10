# 🎲 Distributions

#### Distribution types

Normal distribution - symmetrical

Skewed distribution - weighted on one side

Skew is in direction of the tail

Symmetric means there is one single peak

#### Modality

Unimodal - one single peak

Bimodal - two peaks

Multimodal - multiple peaks

Uniform - no peaks

### Calculations

***

####

#### Types of average

Mean - center by average

Median - center of all values in order (50th percentile) (2nd quartile)

Mode - value of highest frequency (peak of distribution)

Outliers are extreme values

Median and IQR are robust as they're resistant to outliers

Interquartile range - range between quartile 1 and 3

Numpy - Calculating Quartiles

```python
lambda x: np.percentile(x, 25)

np.percentile( value, percentile_num )
np.percentile( value, [percentile_1, percentile_2] )
```

![](https://t20664121.p.clickup-attachments.com/t20664121/71d00a0f-8224-402b-b12f-1e2f3f74649f/image.png)

#### Correlation

Correlation coefficient = -1 to 1, shows us about linear relationships

Positive - higher variables are associate with other higher values

Negative - higher variables are associated with other lower values

The further from 0, the stronger the association (looks more like a line)

#### Covariance

Covariance is the strength between a linear relationship

It ranges from minus infinity to infinity

Higher numbers show a stronger linear relationship

```python
np.cov ( df.val1 , df.val2 )

Example output
[[110669.     228.2]
 [   228.2      0.7]]
```

_Covariable = 228.2_

#### Pearson Correlation

Pearson Correlation is the same but ranges from -1 to 1

```python
from scipy.stats import pearsonr
result, p = pearsonr( df.val1, df.val2 )
```

#### Variance

Is the distance of each data point from the mean and finding the average.

```
Variance = X - (distance from mean)
All variance = SUM( ( X - ( distance from mean ) **2 ) ) / ( number of points )
```

![](https://t20664121.p.clickup-attachments.com/t20664121/9fc8de3c-958f-44af-b1ed-04ceba9081ce/image.png)

Variance = sigma squared

```python
variance = np.var( array_of_values )
```

#### Standard Deviation

The square root of the variance.

Standard deviation is written as sigma.

```python
standard_deviation = variance ** 0.5
```

![](https://t20664121.p.clickup-attachments.com/t20664121/0c51937e-76c1-4a66-9eb2-50832c20bf37/image.png)

```
standard_deviation = np.std( array_of_values )
```

68% of data should be within 1 standard deviation of the mean

95% should be within 2 standard deviations of the mean

99.7% should be within 3 standard deviations of the mean

Over 3 means a very out of place bit of data

![](https://t20664121.p.clickup-attachments.com/t20664121/9f8ddd30-3623-4be9-8122-d03db5bc5235/image.png)

For an individual value

```python
group_mean = np.mean( values )
group_std = np.std( values )
individual = value - group_mean
individual_std = individual / group_std
```

### Random Variables

***

#### Overview

Must be numeric

If categoric, numbers should be used in place of the categories

Random

```python
outcomes = np.random.choice ( range, size = 2, replace = True )
```

_size is how many values to choose_

_replace = False removes that outcome from the pool, replace = True does not_

Generate a random distribution with numpy

```python
random = np.random.choice( [ "heads","tails" ], size = number, p = [ 0.5, 0.5 ] )
```

#### Probability mass function

The probability of an exact random discrete value in a range happening

![](https://t20664121.p.clickup-attachments.com/t20664121/9eb9bea6-7c13-490d-a590-c8523f68793c/image.png)

Binomial Distribution using Probability Mass Functions ( PMF )

```python
from scipy import binom

# Probability of observing an event
binom.pmf ( observed_value, sample, probability )
```

_Example: 6 heads, from 10 flips, with a 0.5 probability of getting a head_

```python
from scipy import binom

# Probability of ovserving more than one event
binom.pmf ( observed_value, sample, probaility ) + binom.pmf ( observed_value, sample, probaility )

# Probability of observing all but two events
1 - ( binom.pmf ( observed_value, sample, probaility ) + scipy.binom.pmf ( observed_value, sample, probaility ) )
```

_If using the 1- method, the scipy codes need to be enclosed in brackets_

#### Probability density function

Like cumulative distribution function but for continuous random variables

Nominal ( mean, std\_distribution )

Cumulative distribution function can be used on a continuous distribution to find the probability of an exact value occurring.

![](https://t20664121.p.clickup-attachments.com/t20664121/b2266710-32b0-49ce-a95b-386d96e4be50/image.png)

#### Cumulative distribution function (discrete and continuous)

The same as the PMF above, but it's accumulative, with the idea that everything increases cumulatively. The calculation will be the probability of all values up to x occurring.

![](https://t20664121.p.clickup-attachments.com/t20664121/908bd6c3-2f51-43fc-a9e2-4b42e955e99b/image.png)

Example: To get the probability of 3-6 observations, you can use

P ( X <= 6 ) - P ( X < 3 )

This functions in Python use scipy.norm.cdf instead of scipy.binom.cdf

Binom is for discrete values

Norm is for continuous

Binomial Distribution using Cumulative Distribution Functions ( CDF )

```python
from scipy import binom

scipy.binom.cdf ( area_of_interest, sample, proability )
```

_Example: <=6, 10 coin flips, 0.5 odds of an observation_

Nominal Distributions using Cumulative Distribution Functions ( CDF )

```python
from scipy.stats import norm

scipy.norm.cdf ( area_of_inerest, mean, std_deviation )
```

_Example: area\_of\_interest = a pokemon having less than 100 attack when the mean is 85 and std deviation is 20_

Cumulative Distribution Function with Standard Error

```
scipy.stats.norm.cdf( liklihood_of_value_or_below, mean, standard_error )
```

_Standard error = standard deviation / (sample\_size \*\* 0.5)_

_\*\* 0.5 means square root_

You can use this to test whether a single value is likely to be a part of the distribution

```python
# Get the CDF value
cdf = stats.norm.cdf( single_value, loc=distribution_mean, scale=distribution_std )

# Establish a required P value
p = 0.05

if p / 2 <= cdf <= 1 - p / 2: print( "likely" )
else: print( "unlikely" )
```

#### Poissons probability mass function

Calculating exact values of discrete values from a random distribution using an average as lambda and influences the covariance. Can be used to model random data.

Lambda is the most occurring average in a distribution

![](https://t20664121.p.clickup-attachments.com/t20664121/bec9fe80-019a-46b8-aedd-03bd062f5f0f/image.png)

With higher lambda in the poisson distribution, the distribution is wider and more flat over a larger area.

![](https://t20664121.p.clickup-attachments.com/t20664121/24965d57-f213-4dae-930b-795a53313628/image.png)

Variance = number\_of\_events x probability x ( 1 - probability )

Adding a number to a variable doesn't change the distribution as there is no range for a single number. Example: Adding points to test scores to grade on a curve.

![](https://t20664121.p.clickup-attachments.com/t20664121/547e1f72-40dd-4b64-b7b8-7d379686e806/image.png)

Scaling a random variable by a constant (a) scales the variance by a squared

Example: Multiplying the random distribution by 2 squares the variance

![](https://t20664121.p.clickup-attachments.com/t20664121/e1c654d7-1827-4207-8dfb-6d856f512e6e/image.png)

The variance of two random variables are the sum of both variances.

![](https://t20664121.p.clickup-attachments.com/t20664121/929a2d0b-966f-4d2d-a34e-488c42ab18a0/image.png)

This only works if x and y are random variables.

Exact values using Poissons Probability Mass Function

```python
from scipy import stats

scipy.stats.poisson.pmf ( event, when_average_is )
```

_Example: event = 8 somethings, when\_average\_is = 10_

Range of a distribution using Poissons cumulative density function

```python
from scipy import stats

scipy.stats.poisson.cmf( event_or_less, when_average_is )
```

_Event includes everything up to and including the number_

Generate a random distribution with scipy

```python
from scipy import stats

rvs = scipy.stats.poisson.rvs(average, size = number)
```

Get a poisson random variables mean

```
mean_value = rvs.mean()
```

Measure Variance in a ditribution

```
variance = np.var( poisson_distirbution )
```

Get values in a percentile with poisson

```
percentile_val = stats.poisson.ppf ( percentile, lambda )
```

_Percentile is a decimal._

### Distributions

***

#### Sampling Distributions

You can create a a set of same-size samples and find the mean, then add those to a list of sample means to create a sample distribution showing the distribution of all mean values in each randomly created dataset.

You can sample any aggregate of a data set - minimum, maximum, mean, median etc

#### Central Limit Theorem

Allows us to describe the sampling distribution of the mean.

Sample sizes over 30 are generally a good idea.

Is the population is not to skewed or the sample is large enough, the mean will be distributed.

Only applies to the mean.

If the original distribution is normally distributed then small sample sizes will align with the distribution.

#### Standard Error

The standard deviation of a sampling distribution is also standard error or the estimate of the mean.

![](https://t20664121.p.clickup-attachments.com/t20664121/4f7c9c64-67a2-4e85-833a-31ef31e8f209/image.png)

As sample size increases the standard error will decrease.

As the standard deviation increases so will the standard error.

#### Unbiased Estimator

The mean of the mean distribution is the population mean.

When the sample distribution value is equal to the actual population value it's an unbiased estimator.

Max is a biased estimator because it is not centered on the population maximum.

#### Confidence Interval

Normally distributed values are within 1.96 standard deviations of the mean.

Multiply 1.96 by the standard error (say it's 2.5)

95% of those samples would be about 2.5 values from the true mean

The confidence interval says we're 95% confident that the original mean is 2.5 each way off the actual population mean. If the observed mean is 18, then we're 95% confident the actual mean is between 15.5 - 20.5

#### P-Values

0.05 or 5% is a good standard. Below is significant, above is not.

A significant p value we reject the null hypothesis.

Type I error - Finding a significant p value when the null hypothesis is true

Type II error - Finding a non significant p value when the null hypothesis is false

You can run a type I test by using a randomised range and calculate the p value using a binomial test.

If the p-value is lower than the significance threshold (0.05) then +1 to an int of false positives.

Then divide by the range loop and see if it's close to the threshold to avoid making a type I error.

The significance threshold for a test is equal to the type I error rate.

### Contingency Tables and chi2

***

Contingency tables can be used to show frequency and proportion.

You can find the expected results if there was a correlation with chi2\_contingency.

You can compare the expected table with with the actual table.

![](https://t20664121.p.clickup-attachments.com/t20664121/2a9eaace-e3f5-4b90-bc0d-063c3f361d51/image.png)

Marginal proportions represent the distribution in a contingency table.

Cross Table

```python
# Creating cross table
new_value = pd.crosstab( df.col1, df.col2 )

# Converting cross table to a proportion
new_new_value = new_value / len( df )

# Summing a marginal proportion
prop = table.sum( axis = 0 or 1 )
```

_Also a cross-tabulation table_

The chi2 values is a degree of freedom that in conjunction with the p-value shows reason to reject the null hypothesis and show statistical significance.

Expected values for no association

```python
from scipy.stats import chi2_contingency
chi2, pval, dof, expected = chi2_contingency( cross_table ) 
```

_Values being lower than the actual results is evidence of association_

chi2 = chi square. Higher than the area of the table is a positive association

expected = expected cross table

### Inferential Statistics

***

Hypothesis testing is a form of inferential statistics. Draw inference about a population from smaller sample data.

Samples do not always reflect the population they came from. Part of inferential statistics is quantifying uncertainty about a population by looking at a smaller sample.

Regression analysis is used to see if relationships in samples reflect the larger population.

#### Z Tests

This is like a T Test to see if an observation is statistically likely within a distribution and can be used on large datasets when you know the distribution standard deviation.

```python
from scipy import stats

# Set a threshhold for tests to be measured against
confidence = 0.05
z_threshhold = stats.norm.ppf( 1 - confidence  / 2 )

# Testing a value
value_z = abs( ( observation - distribution_mean ) / distribution_std )

if value_z  < z_threshhold: "It's statistically likely"
```

#### T-Tests (quantitative testing)

Null hypothesis - The differences are down to chance / variance

Alternative hypothesis - There is an observable testable difference

Null hypothesis - you can generate a null distribution using poissons distribution of means of a sample. You can plot the population mean on the distribution to see if it's within the null distribution.

Assumptions to verify:

\-The sample was randomly selected

\-Observations were independent

\-The data is distributed without outliers or the sample is large enough ( > 40 )

T-tests can still be run without these assumptions being verified, but it should be stated as such.

One-sided t-test

```python
from scipy.stats import ttest_1samp
tstat, p_value = ttest_1samp( sample_distribution, expected_mean )
```

#### P-values

If the sample mean is truly equal to or larger than the population mean.

The probability of observing an average over or equal to the population average on the null distribution if the null hypothesis is true.

(One-tailed test)

![](https://t20664121.p.clickup-attachments.com/t20664121/24ffc985-3d2a-4d92-baea-9409cde57ac9/image.png)

_Average = 30, sample average = 1.24 points higher._

If the sample mean is truly equal to (greater or less than) the population mean.

The probability of observing an average over or below the population average.

(Two-tailed test)

![](https://t20664121.p.clickup-attachments.com/t20664121/12fe18d0-6882-4831-9819-5de7ac0064dd/image.png)

If the sample mean is truly less than the population mean.

The probability of observing an average below the population average.

![](https://t20664121.p.clickup-attachments.com/t20664121/5af90dab-486b-424f-ae2f-df2f4ee7fe9f/image.png)

Example p-values:

Greater than average population (if null hypothesis were true) - 0.031 (3% chance)

Not equal to average population (if null hypothesis were true) - 0.062 (6% chance)

Less than average population (if null hypothesis were true) - 0.969 (97% chance)

If the null hypothesis were true, then the observation would be 3% likely (so it's not).

Rejecting the null hypothesis doesn't mean proving the alternative hypothesis, only shown it to be more consistent with the observation.

Numpy one-sided p-value

```cpp
p_val = np.sum( np_array == "something" ) / len ( full_sample )
```

Numpy two-sided p-value

```python
p_val = np.sum( ( array < 2 ) | ( array > 8 ) ) / len( full_sample )
```

Scipy binom test

```python
from scipy.stats import binom_test
p_val = binom_test( outcome_value, sample_size, probability_of_outcome )
```

_alternative = "less" or "greater" for a one-sided test_
