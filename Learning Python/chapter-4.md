## Introducing Python Object Types

#### Conceptual Hierarchy
* programs > modules > statements > expressions
* expression create & process objects
> Traditionally programming emphasizes *sequence*, *selection*, and *repetition*. But the principle of `objects` is more important.

#### Why Built-in types?
* Makes programs easy to write - most useful tools like collections or search tables are already provided.
* They are components of extensions - 
* more efficient than custom data structures
* They are standard part of the language

#### Core data types
* Numbers
* Strings
* Lists
* Dictionaries
* Tuples
* Files
* Sets
* Other core : Booleans, types, None
* Program unit types (functions, modules, classes)
* Implementation-related types (compiled code, stack tracebacks)

> Python is *dynamically typed* but also *strongly typed*

##### Numbers
* Python 3.x automatically provides extra precision for large numbers
```python
# automatic conversion to long type
print(2 ** 100)
# 1267650600228229401496703205376
```
* how?
    * first convert the result into string type with `str` function.
    * get the length with `len`

* There are two ways to print in Python
    * full precision (as-code `repr`)
    * user-friendly form

#### Strings
* sequence (of one-character strings)
* Sequence Operation
    * sequencial operations assume positional ordering among items, which allows actions like finding length or fetching component with `index`
    * Python allows arbitrary expression pretty much everywhere.
```python
# negative index
S[-1]   # last character
# slicing
S[1:3]  # slicing 1~2
S[:] # return a top-level copy of S
```

* Immutability
    * Strings are immutable in Python
    * immutable objects can never be overwritten
    * core types (number, string, tuple) : immutable
    * lists, dictionaries, can be changed.
```python
S = 'text'
# possible
S = S[1:] + 's'
# not allowed
S[0] = 'z' # TypeError: 'str' object does not support item assignment

# Expand string to list
S = 'string'
L = list(S)     # ['s','t','r','i','n','g']
L[1] = 'p'  # replace in place
''.join(L)  # 'spring'

# use bytearray - bytes/list hybrid
# bytearray supports in-place changes for text but only for text with characters 8-bits wide. It is a distinct hybrid of immutable bytes strings and mutable lists

B = bytearray(b'spam')
B.extend(b'eggs')   # bytearray(b'spameggs')
B.decode()
'spameggs'
```

* Type-specific methods
    * Strings have their own methods
> Ex. `find()`, `replace()`, `split()`, `upper()`, `format()`... etc

`format()` example
```python
# replacing strings per index
'%s, eggs, and %s' % ('spam', 'SPAM!')
> 'spam, eggs, and SPAM!'
'{0}, eggs, and {1}'.format('spam', 'SPAM!')
> 'spam, eggs, and SPAM!'
'{}, eggs, and {}'.format('spam', 'SPAM!')
> 'spam, eggs, and SPAM!'
```

* Python toolset is layered.
    1. Generic operations that span multiple types show up as built-in (len(X), X[0])
    2. Type-specific operations as method calls (aString.upper())

> `dir()` and `help()` to the rescue!
> - `dir()` function lists variables assigned in the caller's scope. Methods are function attributes, so they will show up in the list.
> - `help()` function gives you the explanations.

