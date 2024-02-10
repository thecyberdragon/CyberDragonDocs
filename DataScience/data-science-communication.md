# 💬 Data Science Communication

#### Overview

It's all about storytelling and transforming the data into an easy to understand medium for the audio it's intended for.

> If you put too much math/statistics jargon into a report or presentation for non-technical people, they’re either going to ask you to define things for them or ask for you to clarify upon certain concepts. Hand it over too simplified to a technical audience, however, and they’ll ask you how you came up with your results.

#### Structure

Structure - The sequence to reveal the results of analysis

Observations - What relates to the ultimate goal of the analysis

Relevancy - Cut out the fluff if it doesn't lead to the goal of the analysis

Visuals - Charts should explain themselves and be appropriate

Complexity - Don't let the visuals become noisy

> Data always starts out messy, ugly, and confusing.

People will generally seek high-level takeaways and conclusions then look for granular detail.

#### Audiences

Experts - People who know the subject inside and out.

Technicals - Advanced understandings but in a more practical perspective

Executives - Business and administration people who make decisions with little tech knowledge

Nonspecialists - The least tech knowledge who are interested

#### Audience Adaption

Add information the reader needs to understand the document

Omit information they don't need

Change the information level for the audience

Add examples if it helps the audience

Change the level of the examples for the audience

Change the organisation of the information to lead the reader correctly

Strengthen transitions between observations & data

Write a strong introduction to give the big picture

Create topic sentences

Change sentence style and length

Work on sentence clarity

Use more or different graphics

Break text into usable chunks

Add cross-references to important background or relevant information

Use headings and lists

Use pecial typography to make it look appealing

Who - Who is the intended audience?

What - What kind of knowledge and audience are they?

* Mathphobes - Hate numbers but love concepts
* Bypassers - Understand but have little interest
* Tourists - Keep it simple
* Hot dogs - Know less than they think and need to be guided
* Associates - Other analysists who understand the jargon
* Peers - Understand everything. Anything goes

Why - Why will they be interested?

Where - Where to publish

When - When does x need to see it?

How - How to package and format the report. What appearance? Are there any specialty items? Is it accessible?

#### Tables

Set table headers

```python
import pandas as pd

pd.set_option("colheader_justify", "center")
```

#### Links

Structure of a report

{% embed url="https://www.stat.cmu.edu/~brian/701/notes/paper-structure.pdf" %}

Audience Analysis

[https://mcmassociates.io/textbook/aud.html](https://mcmassociates.io/textbook/aud.html)

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
