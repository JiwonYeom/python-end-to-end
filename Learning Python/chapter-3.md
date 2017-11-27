# Chapter 3. How you run programs
```Python
import sys
print(sys.platform)
print(2 ** 100)
x = 'Spam'
print(x * 8)
```

* Strem redirection
```Python
python script1.py > saveit.txt
```

##### Unix-Style Executable Scripts: `#!`

- Unix Script Basics
    - First line is special: Starts with a line that begins with `#!`, followed by path to the Python interpreter
    - Have executable privileges. (by `chmod +x file.py`)

- Unix env Lookup Trick
    - It's not reqired to hardcode path to Python interpreter.
    - As long as the file has access to env, this will work. Since Python can be installed in different places, this way of reference is recommended.

```
#!/usr/bin/env python
```
##### Module Imports and Reloads
- Module-based services model is the core idea behind Python program architecture.
- Modules can be imported only once per file, but if needed use `reload`
- `Python 3.x` moved the `reload` to `imp` standard library module.

##### The Grander Module Story: Attributes
- Imports & reloads provide natural program launch option.
- But it can also be thought as library.
- Module is mostly just a pacckage of variable names(`namespace`).
- Names within the package is called `attributes`.
- Attribute: variable name attached to a specific object (like a module)
```Python
import myfile
myfile.title
```

```Python
from myfile import title
title
```