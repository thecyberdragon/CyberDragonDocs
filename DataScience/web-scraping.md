# 🔽 Web Scraping

## <mark style="color:red;">Before scraping</mark>

***

Check the website rules on data. Scraping shouldn't usually be for commercial use.

No more than 1 request per webpage per second.

## <mark style="color:red;">Scraping</mark>

***

### <mark style="color:yellow;">Getting a URL request</mark>

```python
import requests

webpage = requests.get( "url_string" )
webpage_contents = webpage.contents
```

### <mark style="color:yellow;">Import Soup</mark>

```python
from bs4 import BeautifulSoup

soup = BeautifulSoup( html_file, html.parser )
```

_Other parsers are possible like lxml and html5lib_

### <mark style="color:yellow;">Scraping with Soup</mark>

```python
webpage = responses.get( "webpage_url" )
soup = BeautifulSoup( webpage.text, "html.parser" )
```

### <mark style="color:yellow;">Tags</mark>

BeautifulSoup breaks the page down into HTML tags.

Navigable strings are the strings in tags.

```python
# The div name and attributes
soup.div.name
soup.div.attrs

# First paragraph in the html
soup.p

# String associated with a tag
soup.div.string
```

![](https://images4.imagebam.com/00/6e/5b/MES1OQO\_o.png)

```python
# Get the heading 1
soup.h1

# Get shildren of tag
for child in soup.ul.children:
  print( child )

# Get the parent of a tag
for parent in soup.li.parents:
  print( parent )
```

### <mark style="color:yellow;">Dev Tools</mark>

Inspect the HTML in browser dev tools to find the HTML of what you want to scrape.

### <mark style="color:yellow;">Finding content</mark>

```python
# Return the first tag found
soup.find( tag )

# Return the text
soup.find( tag ).text

# Return all matching tags
soup.find_all( tag )

# Using a list
soup.find( [ "list", "of", "tags" ] )
```

### <mark style="color:yellow;">Using regex in soup find and find\_all</mark>

```python
import re

soup.find_all( re.compile( "regex_expression" ) )
```

_re.compile( " h\[1-9] " ) will return all headers_

### <mark style="color:yellow;">Using attributes to find elements</mark>

```python
# Find all banners by attribute: class, banner
soup.find_all( attrs= { "class":"banner" } )

# Use multiple attributes
soup.find_all(  attrs={ "class":"banner", "id":"something" })
```

### <mark style="color:yellow;">CSS Selection</mark>

```python
# .select() is for CSS

# Select by class name
soup.select( ".class_name" )

# Select by id
soup.select( "#id_name" )

# Finding a link and scraping the target
for link in soup.select( ".hyperlink > a" ):
  webpage = requests.get( link )
  new_soup = BeautifulSoup(webpage)
```

### <mark style="color:yellow;">Reading text</mark>

```python
# Get one combined string
soup.get_text( )

# Split by tag
soup.get_text( "|" )

# Example
name = soup.select( ".name" )[0].get_text( )
```

## <mark style="color:red;">Resources</mark>

***

{% embed url="https://www.codecademy.com/article/http-requests" %}

{% embed url="https://www.codecademy.com/article/use-devtools" %}

{% embed url="https://www.w3schools.com/TAGS/default.asp" %}
