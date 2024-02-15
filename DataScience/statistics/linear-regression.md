# 🎲 Linear Regression

### <mark style="color:yellow;">Overview</mark>

This is a modelling technique to understand the relationship between a quantitative value and something else.

Fitting a linear line onto the data - the line of best fit.

```
y = mx + b
```

X and Y are the data variables\
b = the intercept, where the outcome variable hits the y axis when the predictor 0\
m = the slope (how steep the line is)

The slope is the rise (vertical) and run (horizontal) increments of the line.\
\+ slope is a positive line\
\- slope is a negative line

Assumptions made with linear regression:\
\-A linear relationship exists\
\-Residuals should be normally distributed\
\-Homoscedasticity across residuals

### <mark style="color:yellow;">Ordinary Least Squares</mark>

```
y = mx + b + error
```

The best line minimises the total squared error for all data points. (loss)

![](https://images4.imagebam.com/1f/ca/55/MES1OO1\_o.png)

Loss = distance\_from\_line squared + for all points\
Loss = ( -1 )2 + ( 3 )2 = 1 + 9 = 10

#### Fitted values and residuals

![](https://images4.imagebam.com/36/7d/ac/MES1OO2\_o.png)

```python
import statsmodels.api as sm

# Generating the model
model = sm.OLS.from_formula( "y ~ x", data = dataset )
results = model.fit( )

# Calculate fitted values and residuals
fitted = results.predict( dataset.x )
residuals = dataset.y - fitted

# Summary of the results
results.params
results.summary ( )
```

### <mark style="color:yellow;">Testing residuals distribution and variance</mark>

Plot the residuals on a histogram and check the distribution.\
Does this satisfy the normality assumption?

Homoscedasticity - do the residuals have roughly equal variance?

Plot them on a scatter graph (residuals, fitted\_values) to see if it satisfies the assumption.\
The plot should look random and centered at 0.

Patters or asymmetry indicate the assumption is not met and linear regression might not be appropriate.

### <mark style="color:yellow;">Line of best fit on a binomial scatter</mark>

Get the grouped mean of each binary value and draw a line from mean to mean.

![](https://images4.imagebam.com/21/8d/0c/MES1OO0\_o.png)

### <mark style="color:yellow;">X Matrix</mark>

Categorical values can be represented with an x matrix.

If plotting for categorical values, you can use patsy to dematrices the dataset and return for x a list of binary lists representing what category it is.

sausage\
eggs\
eggs\
milk\
milk

Would return

```
[[1. 0. 0.]
 [1. 1. 0.]
 [1. 1. 0.]
 [1. 0. 1.]
 [1. 0. 1.]]
```

This doesn't contain a column for sausage, as the remaining missing 1's will all be for this value.

This is the reference category for the model as all 0's means that entry must be for sausage.\
The intercept is the average for the reference column.

For all non reference columns:\
y = b + mx +- mx +- mx ....\
x = the binary values of 1 or 0\
m = the slope of that value\
b = constant for all values
