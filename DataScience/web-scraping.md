# 🔽 Web Scraping

#### Before scraping

Check the website rules on data. Scraping shouldn't usually be for commercial use.

No more than 1 request per webpage per second.

#### Getting a URL request

```python
import requests

webpage = requests.get( "url_string" )
webpage_contents = webpage.contents
```

#### Import Soup

```python
from bs4 import BeautifulSoup

soup = BeautifulSoup( html_file, html.parser )
```

_Other parsers are possible like lxml and html5lib_

#### Scraping with Soup

```python
webpage = responses.get( "webpage_url" )
soup = BeautifulSoup( webpage.text, "html.parser" )
```

#### Tags

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

![](https://t20664121.p.clickup-attachments.com/t20664121/8c0d2f9f-46a6-47cf-8e6c-25ca809f246a/image.png)

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

#### Dev Tools

Inspect the HTML in browser dev tools to find the HTML of what you want to scrape.

#### Finding content

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

Using regex in soup find and find\_all

```python
import re

soup.find_all( re.compile( "regex_expression" ) )
```

_re.compile( " h\[1-9] " ) will return all headers_

Using attributes to find elements

```python
# Find all banners by attribute: class, banner
soup.find_all( attrs= { "class":"banner" } )

# Use multiple attributes
soup.find_all(  attrs={ "class":"banner", "id":"something" })
```

#### CSS Selection

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

#### Reading text

```python
# Get one combined string
soup.get_text( )

# Split by tag
soup.get_text( "|" )

# Example
name = soup.select( ".name" )[0].get_text( )
```

#### Resources

{% embed url="https://www.codecademy.com/article/http-requests" %}

{% embed url="https://www.codecademy.com/article/use-devtools" %}

{% embed url="https://www.w3schools.com/TAGS/default.asp" %}
