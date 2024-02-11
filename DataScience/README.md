# 🧬 Overview

## <mark style="color:red;">Principles</mark>

***

Columns are things to measure\
Rows are instances, observations, or entities\
Data should be tidy

## <mark style="color:red;">Types of data</mark>

***

<mark style="color:yellow;">Numerical</mark> - Measurements are numerical with units (1.0, 2.5, 8, -56)\
<mark style="color:yellow;">Continuous</mark> - measurements\
<mark style="color:yellow;">Discrete</mark> - counts\
<mark style="color:yellow;">Categorical</mark> - Categories describe characteristics with words\
<mark style="color:yellow;">Nominal</mark> - Describes something\
<mark style="color:yellow;">Ordinal</mark> - A ranking\
<mark style="color:yellow;">Binary values</mark> - Two possible values

_id in a table is a number but it's a label so it's categorical_

Dichotomous values are true or false\
Rankings are ordinal values - ordered

A convenience sample is a data subset for preliminary analysis but not good enough for a comprehensive analysis and introduces bias

## <mark style="color:red;">Five types of data analysis</mark>

***

### <mark style="color:yellow;">**Descriptive**</mark>

Usually the first step. Summary statistics.\
Central tendency and spread. Mean, mode, median, St dev, quartiles etc.\
Visualisation

### <mark style="color:yellow;">**Exploratory**</mark>

Look for relationships between variables.\
Spotting correlation\
Cluster anaysis (machine learning)\
PCA - principle component analysis\
K - clustering\
Rand statistics\
Like confidence coefficient, a rand close to 1.0 is strong

### <mark style="color:yellow;">**Inference**</mark>

A/B test.\
Split a sample in half randomly and test A or B.\
Calculate within 5% chance the result is down to random chance\
\-Sample size must be 10% of the extrapolated population\
\-The sample must be randomly selected and represent the population\
\-One variable should be tested at a time

### <mark style="color:yellow;">**Causal**</mark>

\-Change one variable at a time\
\-Carefully control all other variables\
\-Can be repeated with the same results multiple times

Causal correlations require\
\-Advanced techniques\
\-Meeting strict conditions\
\-Appropriate statistical tests

### <mark style="color:yellow;">**Predictive**</mark>

Uses predictive analysis and supervised machine learning.\
\-Regression models\
\-Support vector machines\
\-Deep learning convolutional neural networks

## <mark style="color:red;">Bias in data</mark>

***

\-Selection bias (not randomising your data / selecting the data)\
\-Automation bias (relying entirely on automation)\
\-Algorithmic bias (When an algorithm produces repeatable errors and unfair outcomes)\
\-Evaluation bias (Algorithm testing a non-representative dataset)

Evaluation biases:\
\-Confirmation bias (seek answers we already think)\
\-Overgeneralisation bias (Extending generalisations between datasets)\
\-Reporting bias (only reporting positive results)

## <mark style="color:red;">Data Collection</mark>

***

### <mark style="color:yellow;">**PII Personal Identifying information**</mark>

Consent - Obtain it\
Ownership - individuals own their data\
Intention - How is the data to be used and stored\
Privacy - Keep info private, especially PII

### <mark style="color:yellow;">**Types**</mark>

Static data - collected onece and doesn't change (like a survey)\
Non-static - data changes and updates

### <mark style="color:yellow;">**General**</mark>

Validity is the relationship between the data and its purpose\
Does this variable measure what I think it does?

## <mark style="color:red;">General Steps</mark>

***

\-Formulate questions that can be answered with data\
\-Clean and transform the dataset\
\-Apply correct statistical techniques to answer the question\
\-Support the analysis with visualisations\
\-Summarise the main takeaways

### <mark style="color:yellow;">Portfolio rules</mark>

Tableu & Power BI -> don't take screenshots. Publish the graph (keep the interactivity)\
Code files -> Save as the code file, not a document\
Written reports -> Use images from tableu etc, it's OK
