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

* There are two ways to print Python
    * full precision (as-code `repr`)
    * user-friendly form