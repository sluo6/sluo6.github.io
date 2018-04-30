---
layout: post
title:  "Python notes(2)"
date:   2017-04-29 22:50:15
author: Shangwen
---

## Regular expression

Can be accessed by `re` module.
Basic syntax example:
```python
import re

pattern = r"pam"

match = re.search(pattern, "eggspamsausage")
if match:
    print(match.group())
    print(match.start())
    print(match.end())
    print(match.span())
```
Here `r` means "raw string". `group()` gives the match string. 
Output:
```python
>>>
pam
4
7
(4, 7)
>>>
```
### Search and Replace
Syntax: `re.sub(pattern, repl, string, max=0)`
Example:
```python
import re

str = "My name is David. Hi David."
pattern = r"David"
newstr = re.sub(pattern, "Amy", str)
print(newstr)
```
### Mini Cheatsheet
+ `.` any character
+ `^` start of string
+ `$` end of string
+ `[abc]` any one character of 'a', 'b', or 'c'
+ `[A-Za-z]` any one letter of any case
+ `[^A-Z]` not upper class letters
+ `*` zero or more repetitions of the previous thing
+ `+` one or more repetitions of the previous thing
+ `?` zero or one of the previous thing
+ `{x,y}` between 'x' and 'y' repetitions. default x=0, y=infinity
+ `(abc)` "abc" as a group, taken as a whole when checking for repetitions
+ `|` or
+ `\2` match two times
+ `\d \s \w` digits, whitespace, word characters
+ `\D \S \W` opposite to above

