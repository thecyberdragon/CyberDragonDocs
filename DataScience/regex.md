---
description: Regular Expressions
---

# ❔ Regex

## <mark style="color:red;">Character Sets</mark>

***

### <mark style="color:yellow;">Literal</mark>

```
sausages = sausages
```

_Find entire or partial string in results_

### <mark style="color:yellow;">Alternation</mark>

```
sausages|sosig = sausages or sosig
```

### <mark style="color:yellow;">Character Sets</mark>

```
sausag[es] = sausage or sausags
[pog] = p, o, or g but not pog
```

_\[ ] matches one character from the set_

### <mark style="color:yellow;">Negative character sets</mark>

```
[^pog] = not p or o or g
```

## <mark style="color:red;">Wildcards</mark>

***

```
. = any character
\. = full stop
```

### <mark style="color:yellow;">Range</mark>

```
[a-e] = a b c d or e in a range
[A-Z] = capital letters
[a-z] = lower case letters
[0-9 = numbers]
[A-Za-z] = all letters
```

### <mark style="color:yellow;">Shorthand</mark>

```
\w = any letter or number or underscore = [A-Za-z0-9_]
\d = digit = any number
\s whitespace = [ \t\r\n\f\v] = space, tab, return, break, form feed, vertical tab
```

### <mark style="color:yellow;">Negative shorthand</mark>

```
\W = non-word character = [^A-Za-z0-9_]
\D = non digit = [^0-9]
\S = non whitespace = [^ \t\r\n\f\v]
```

## <mark style="color:red;">Functions</mark>

***

### <mark style="color:yellow;">Grouping</mark>

```
I love (sausage|sosig) = I love sausages or I love sosig
```

### <mark style="color:yellow;">Quantifiers</mark>

```
\w{3} = \w\w\w
\w{4,7} = \w\w\w\w to \w\w\w\w\w\w\w
hi{5} = hiiiii
```

_Quantifiers favour larger lengths_

### <mark style="color:yellow;">Optional Quantifiers</mark>

```
? = 0 or 1 occurence
humou?r = humor or humour
Option word (can )?go here
\? = noirmal question mark
```

### <mark style="color:yellow;">Kleene Star</mark>

```
* = 0 or more times
meo*w = mew, meow, meooooow, meooooooooooooooooooooooooooooooow etc

+ = 1 or more times
meo+w = meow, meooooow, meooooooooooooooooooooooooooooooow, but not mew

\* and \+ are the escaped literal characters
```

### <mark style="color:yellow;">Anchors</mark>

```
^Something = Something must be at the beginning
Ending$ = Must end with Ending
\^ and \$ escape the characters
```

### <mark style="color:yellow;">Case insensitivity</mark>

```
(?i)Can_Be-ANy_CaSE
```

### <mark style="color:yellow;">Links</mark>

[https://regexr.com](https://regexr.com)[https://content.codecademy.com/courses/regex/onyourexcitingjourneylearningtocodeyouwillfindthis.gif](https://content.codecademy.com/courses/regex/onyourexcitingjourneylearningtocodeyouwillfindthis.gif)
