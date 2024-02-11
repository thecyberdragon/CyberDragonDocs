# 💬 Data Science Communication

## <mark style="color:red;">Overview</mark>

***

It's all about storytelling and transforming the data into an easy to understand medium for the audio it's intended for.

> If you put too much math/statistics jargon into a report or presentation for non-technical people, they’re either going to ask you to define things for them or ask for you to clarify upon certain concepts. Hand it over too simplified to a technical audience, however, and they’ll ask you how you came up with your results.

## <mark style="color:red;">Structure</mark>

***

<mark style="color:yellow;">Structure</mark> - The sequence to reveal the results of analysis\
<mark style="color:yellow;">Observations</mark> - What relates to the ultimate goal of the analysis\
<mark style="color:yellow;">Relevancy</mark> - Cut out the fluff if it doesn't lead to the goal of the analysis\
<mark style="color:yellow;">Visuals</mark> - Charts should explain themselves and be appropriate\
<mark style="color:yellow;">Complexity</mark> - Don't let the visuals become noisy

> Data always starts out messy, ugly, and confusing.

People will generally seek high-level takeaways and conclusions then look for granular detail.

## <mark style="color:red;">Audiences</mark>

***

<mark style="color:yellow;">Experts</mark> - People who know the subject inside and out.\
<mark style="color:yellow;">Technicals</mark> - Advanced understandings but in a more practical perspective\
<mark style="color:yellow;">Executives</mark> - Business and administration people who make decisions with little tech knowledge\
<mark style="color:yellow;">Nonspecialists</mark> - The least tech knowledge who are interested

### <mark style="color:yellow;">Audience Adaption</mark>

* Add information the reader needs to understand the document
* Omit information they don't need
* Change the information level for the audience
* Add examples if it helps the audience
* Change the level of the examples for the audience
* Change the organisation of the information to lead the reader correctly
* Strengthen transitions between observations & data
* Write a strong introduction to give the big picture
* Create topic sentences
* Change sentence style and length
* Work on sentence clarity
* Use more or different graphics
* Break text into usable chunks
* Add cross-references to important background or relevant information
* Use headings and lists
* Use special typography to make it look appealing

### <mark style="color:yellow;">Audience Types</mark>

<mark style="color:yellow;">Mathphobes</mark> - Hate numbers but love concepts\
<mark style="color:yellow;">Bypassers</mark> - Understand but have little interest\
<mark style="color:yellow;">Tourists</mark> - Keep it simple\
<mark style="color:yellow;">Hot dogs</mark> - Know less than they think and need to be guided\
<mark style="color:yellow;">Associates</mark> - Other analysists who understand the jargon\
<mark style="color:yellow;">Peers</mark> - Understand everything. Anything goes

Why - Why will they be interested?\
Where - Where to publish\
When - When does x need to see it?\
Who - Who is the intended audience?\
What - What kind of knowledge and audience are they?\
How - How to package and format the report. What appearance? Are there any specialty items? Is it accessible?

## <mark style="color:red;">Misc</mark>

***

### <mark style="color:yellow;">Set table headers</mark>

```python
import pandas as pd

pd.set_option("colheader_justify", "center")
```

### <mark style="color:yellow;">Links</mark>

Structure of a report

{% embed url="https://www.stat.cmu.edu/~brian/701/notes/paper-structure.pdf" %}

Audience Analysis

{% embed url="https://mcmassociates.io/textbook/aud.html" %}

How to write reports

{% embed url="https://crayondata.ai/write-data-analysis-reports-lesson-2-know-audience/" %}

#### To figure out wtf I was doing...

```
css = '''
        <html>
          <link rel="stylesheet" type="text/css" href="df_style.css"/>
          <body>
            {table}
          </body>
        </html>
      '''

# OUTPUT AN HTML FILE
with open("index.html","w") as fp:
    fp.write(css.format(table=df.to_html(classes=["dataframe", "table"])))
```
