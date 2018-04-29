---
layout: post
title:  "Python notes(1)"
date:   2017-04-28 23:32:56
author: Shangwen
---

## List, tuple, dictionary, set

+ List: ['apple', 'pear', 'orange']; can be multi-dimensional;
+ tuple: ('apple', 'pear', 'orange'); immutable; ordered;
+ dictionary: {'apple':2, 'pear':3, 'orange':5}; key-value map;
+ set: {'a', 'b', 'c', 'd'}; unordered; no duplicates;

## Hiding Data

Weakly private attributes and methods are named using `_attibute` or `_method` convention.
Weakly private variables CAN be accessed from outside of class.
`from module import *` won't import variables named as `_variable`.

Strongly private attributes are named using `__attribute`. They can not be accessed directly from outside class.
To access variable `__a` of class `b` from outside class, syntax `_b__a` should be used.

## Lambda

```
   #named function
   def polynomial(x):
       return x**2 + 7*x + 2
   print(polynomial(-4))
   
   #lambda
   print((lambda x: x**2 + 5*x + 4) (-4))
   ```
   
## Decorators

Rudimentary way:
```
def decor(func):
  def wrap():
    print("============")
    func()
    print("============")
  return wrap

def print_text():
  print("Hello world!")

decorated = decor(print_text)
decorated()
```
Elegant way:
```
def decor(func):
    def wrap():
        print("============")
        func()
        print("============")
    return wrap

@decor
def print_text():
    print("Hello world!")

print_text();
```
