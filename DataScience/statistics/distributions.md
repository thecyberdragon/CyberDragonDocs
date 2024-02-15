# 🎲 Distributions

## <mark style="color:red;">Distributions</mark>

***

### <mark style="color:yellow;">Distribution types</mark>

<mark style="color:yellow;">Normal distribution</mark> - symmetrical\
<mark style="color:yellow;">Skewed distribution</mark> - weighted on one side

Skew is in direction of the tail\
Symmetric means there is one single peak

### <mark style="color:yellow;">Modality</mark>

<mark style="color:yellow;">Unimodal</mark> - one single peak\
<mark style="color:yellow;">Bimodal</mark> - two peaks\
<mark style="color:yellow;">Multimodal</mark> - multiple peaks\
<mark style="color:yellow;">Uniform</mark> - no peaks

### <mark style="color:yellow;">Calculations & Types of average</mark>

<mark style="color:yellow;">Mean</mark> - center by averag\
<mark style="color:yellow;">Median</mark> - center of all values in order (50th percentile) (2nd quartile)\
<mark style="color:yellow;">Mode</mark> - value of highest frequency (peak of distribution)

Outliers are extreme values\
Median and IQR are robust as they're resistant to outliers\
Interquartile range - range between quartile 1 and 3

Numpy - Calculating Quartiles

```python
lambda x: np.percentile(x, 25)

np.percentile( value, percentile_num )
np.percentile( value, [percentile_1, percentile_2] )
```

![](https://images4.imagebam.com/69/25/fe/MES1OPM\_o.png)

### <mark style="color:yellow;">Correlation</mark>

Correlation coefficient = -1 to 1, shows us about linear relationships

<mark style="color:yellow;">Positive</mark> - higher variables are associate with other higher values\
<mark style="color:yellow;">Negative</mark> - higher variables are associated with other lower values

The further from 0, the stronger the association (looks more like a line)

### <mark style="color:yellow;">Covariance</mark>

Covariance is the strength between a linear relationship\
It ranges from minus infinity to infinity\
Higher numbers show a stronger linear relationship

```python
np.cov ( df.val1 , df.val2 )

Example output
[[110669.     228.2]
 [   228.2      0.7]]
```

_Covariable = 228.2_

### <mark style="color:yellow;">Pearson Correlation</mark>

Pearson Correlation is the same but ranges from -1 to 1

```python
from scipy.stats import pearsonr
result, p = pearsonr( df.val1, df.val2 )
```

### <mark style="color:yellow;">Variance</mark>

Is the distance of each data point from the mean and finding the average.

```
Variance = X - (distance from mean)
All variance = SUM( ( X - ( distance from mean ) **2 ) ) / ( number of points )
```

![](https://images4.imagebam.com/05/a0/b2/MES1OPV\_o.png)

Variance = sigma squared

```python
variance = np.var( array_of_values )
```

### <mark style="color:yellow;">Standard Deviation</mark>

The square root of the variance.\
Standard deviation is written as sigma.

```python
standard_deviation = variance ** 0.5
```

![](https://images4.imagebam.com/52/9d/d5/MES1OPS\_o.png)

```
standard_deviation = np.std( array_of_values )
```

68% of data should be within 1 standard deviation of the mean\
95% should be within 2 standard deviations of the mean\
99.7% should be within 3 standard deviations of the mean\
Over 3 means a very out of place bit of data

![](https://images4.imagebam.com/f5/7e/52/MES1OPU\_o.png)

For an individual value

```python
group_mean = np.mean( values )
group_std = np.std( values )
individual = value - group_mean
individual_std = individual / group_std
```

### <mark style="color:yellow;">Random Variables</mark>

Must be numeric\
If categoric, numbers should be used in place of the categories

Random

```python
outcomes = np.random.choice ( range, size = 2, replace = True )
```

_size is how many values to choose_\
_replace = False removes that outcome from the pool, replace = True does not_

Generate a random distribution with numpy

```python
random = np.random.choice( [ "heads","tails" ], size = number, p = [ 0.5, 0.5 ] )
```

### <mark style="color:yellow;">Probability mass function</mark>

The probability of an exact random discrete value in a range happening

![](https://images4.imagebam.com/68/0f/40/MES1OPP\_o.png)

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

### <mark style="color:yellow;">Probability density function</mark>

Like cumulative distribution function but for continuous random variables

Nominal ( mean, std\_distribution )

Cumulative distribution function can be used on a continuous distribution to find the probability of an exact value occurring.

![](https://images4.imagebam.com/bd/d2/8d/MES1OPO\_o.png)

### <mark style="color:yellow;">Cumulative distribution function (discrete and continuous)</mark>

The same as the PMF above, but it's accumulative, with the idea that everything increases cumulatively. The calculation will be the probability of all values up to x occurring.

![](https://images4.imagebam.com/0d/ab/b3/MES1OPK\_o.png)

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

### <mark style="color:yellow;">Poissons probability mass function</mark>

Calculating exact values of discrete values from a random distribution using an average as lambda and influences the covariance. Can be used to model random data.

Lambda is the most occurring average in a distribution

![](https://images4.imagebam.com/c3/ed/35/MES1OPQ\_o.png)

With higher lambda in the poisson distribution, the distribution is wider and more flat over a larger area.

![](https://images4.imagebam.com/b3/1b/15/MES1OPR\_o.png)

Variance = number\_of\_events x probability x ( 1 - probability )

Adding a number to a variable doesn't change the distribution as there is no range for a single number. Example: Adding points to test scores to grade on a curve.

![](https://images4.imagebam.com/df/c8/f5/MES1OPX\_o.png)

Scaling a random variable by a constant (a) scales the variance by a squared

Example: Multiplying the random distribution by 2 squares the variance

![](https://images4.imagebam.com/1c/3d/fe/MES1OPY\_o.png)

The variance of two random variables are the sum of both variances.

![](https://images4.imagebam.com/85/91/0f/MES1OPW\_o.png)

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

### <mark style="color:yellow;">Sampling Distributions</mark>

You can create a set of same-size samples and find the mean, then add those to a list of sample means to create a sample distribution showing the distribution of all mean values in each randomly created dataset.

You can sample any aggregate of a data set - minimum, maximum, mean, median etc

### <mark style="color:yellow;">Central Limit Theorem</mark>

Allows us to describe the sampling distribution of the mean.\
Sample sizes over 30 are generally a good idea.\
Is the population is not to skewed or the sample is large enough, the mean will be distributed.\
Only applies to the mean.

If the original distribution is normally distributed then small sample sizes will align with the distribution.

### <mark style="color:yellow;">Standard Error</mark>

The standard deviation of a sampling distribution is also standard error or the estimate of the mean.

![](https://images4.imagebam.com/45/bb/20/MES1OPT\_o.png)

As sample size increases the standard error will decrease.\
As the standard deviation increases so will the standard error.

### <mark style="color:yellow;">Unbiased Estimator</mark>

The mean of the mean distribution is the population mean.\
When the sample distribution value is equal to the actual population value it's an unbiased estimator.\
Max is a biased estimator because it is not centered on the population maximum.

### <mark style="color:yellow;">Confidence Interval</mark>

Normally distributed values are within 1.96 standard deviations of the mean.

Multiply 1.96 by the standard error (say it's 2.5)

95% of those samples would be about 2.5 values from the true mean

The confidence interval says we're 95% confident that the original mean is 2.5 each way off the actual population mean. If the observed mean is 18, then we're 95% confident the actual mean is between 15.5 - 20.5

### <mark style="color:yellow;">P-Values</mark>

0.05 or 5% is a good standard. Below is significant, above is not.

A significant p value we reject the null hypothesis.

Type I error - Finding a significant p value when the null hypothesis is true\
Type II error - Finding a non significant p value when the null hypothesis is false

You can run a type I test by using a randomised range and calculate the p value using a binomial test.\
If the p-value is lower than the significance threshold (0.05) then +1 to an int of false positives.\
Then divide by the range loop and see if it's close to the threshold to avoid making a type I error.

The significance threshold for a test is equal to the type I error rate.

### <mark style="color:yellow;">Contingency Tables and chi2</mark>

Contingency tables can be used to show frequency and proportion.\
You can find the expected results if there was a correlation with chi2\_contingency.\
You can compare the expected table with with the actual table.

![](https://images4.imagebam.com/79/f9/8e/MES1OPL\_o.png)

Marginal proportions represent the distribution in a contingency table.

#### Cross Table

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

## <mark style="color:red;">Inferential Statistics</mark>

***

Hypothesis testing is a form of inferential statistics. Draw inference about a population from smaller sample data.

Samples do not always reflect the population they came from. Part of inferential statistics is quantifying uncertainty about a population by looking at a smaller sample.

Regression analysis is used to see if relationships in samples reflect the larger population.

### <mark style="color:yellow;">Z Tests</mark>

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

### <mark style="color:yellow;">T-Tests (quantitative testing)</mark>

Null hypothesis - The differences are down to chance / variance\
Alternative hypothesis - There is an observable testable difference

Null hypothesis - you can generate a null distribution using poissons distribution of means of a sample. You can plot the population mean on the distribution to see if it's within the null distribution.

Assumptions to verify:\
\-The sample was randomly selected\
\-Observations were independent\
\-The data is distributed without outliers or the sample is large enough ( > 40 )

T-tests can still be run without these assumptions being verified, but it should be stated as such.

#### One-sided t-test

```python
from scipy.stats import ttest_1samp
tstat, p_value = ttest_1samp( sample_distribution, expected_mean )
```

#### P-values

If the sample mean is truly equal to or larger than the population mean.

The probability of observing an average over or equal to the population average on the null distribution if the null hypothesis is true.

(One-tailed test)

![](https://images4.imagebam.com/8c/51/14/MES1OPZ\_o.png)

_Average = 30, sample average = 1.24 points higher._\
If the sample mean is truly equal to (greater or less than) the population mean.\
The probability of observing an average over or below the population average.

(Two-tailed test)

![](https://images4.imagebam.com/89/0d/47/MES1OQ0\_o.png)

If the sample mean is truly less than the population mean.\
The probability of observing an average below the population average.

![](https://images4.imagebam.com/78/1e/bb/MES1OPN\_o.png)

Example p-values:

Greater than average population (if null hypothesis were true) - 0.031 (3% chance)\
Not equal to average population (if null hypothesis were true) - 0.062 (6% chance)\
Less than average population (if null hypothesis were true) - 0.969 (97% chance)

If the null hypothesis were true, then the observation would be 3% likely (so it's not).

Rejecting the null hypothesis doesn't mean proving the alternative hypothesis, only shown it to be more consistent with the observation.

#### Numpy one-sided p-value

```cpp
p_val = np.sum( np_array == "something" ) / len ( full_sample )
```

#### Numpy two-sided p-value

```python
p_val = np.sum( ( array < 2 ) | ( array > 8 ) ) / len( full_sample )
```

#### Scipy binom test

```python
from scipy.stats import binom_test
p_val = binom_test( outcome_value, sample_size, probability_of_outcome )
```

_alternative = "less" or "greater" for a one-sided test_
