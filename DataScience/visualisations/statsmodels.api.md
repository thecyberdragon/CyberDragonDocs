# ⚙ Statsmodels.api

```python
import statsmodels.api as sm
```

#### Line of best fit using OLS

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

_params shows the intercept and height (slope)_

_model is a new data set we don't see called the x matrix_

The order of the x and y matter

You're predicting x from y

#### Predicting a value

```cs
new_data = { "parameter": [ value ] }
prediction = results.predict( new_data )
```

_For binary values, the slope is the difference in binary means, and the intercept is the y of the x axis = 0, or a False of the binary._
