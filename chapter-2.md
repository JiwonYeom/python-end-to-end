# Chapter 2 : How Python Runs Programs
* Python interpreter : Python is a language, but also a software package called `interpreter`.

* Interpreter executes other programs.

* When python package is installed, minimal package that is going to be generated is an interpreter and a support library. 

* `.py` for "imported" files, but for general purpose too.

* Step by Step
    1. Commanded to run
    2. Byte code compilation: Python decomposes source statements into group of byte code instructions. 
        * Before version 3.2, the byte code will be stored with .pyc extension. (if python has permission to write)
        * After 3.2, it saves files in a subdirectory named `__pycache__`
        * Source Check: those byte code files will be run without recompiling
        * Version Check: check if Python version has changed.
        * If not writable, it will write in memory & discard it
        * Byte code is saved in files only for files that are **imported**.
    3. Shipped to PVM (Python Virtual Machine): Runtime engine for Python. Big code loop that iterates through your byte codes. Actually runs your code.

* Byte code is a Python-specific representation. There is no build. Not binary machine code. 

* No differences in dev / execution environment. Real-time running. No need for precompiling. 

* All we have in Python is runtime.

> Personal thoughts: Python does not compile the whole body of code. Not even for function / class creations. This is unlike more static languages like `C`, `C++`, `Java`, etc. Reversely speaking, the latter languages compile & run. This is probably why running a `Java` compilation will end up pre-alert of exception whilst script languages execute until the error is found.

#### Execution Model Variations
* Python implementation alternatives
    * `CPython` : Standard implementation.
    * `PyPy` runs programs much faster. 
    * `Jython` : different runtime architecture to call out to Java
    * `IronPython` : different runtime architecture to call out to .NET
    * `Stackless` : oriented towards concurrency - does not save state on C language, allows small stack architectures, efficient multiprocessing options, etc.
    * `PyPy` : JIT compiler, provides sandbox models (untrused code testing). Includes support for Stackless. Aims for performance & speed  

#### Execution Optimization Tool
* Includes tools like `Cython`(python / C), `Shed Skin`(python / C++), `Psyco`(focus on running Python faster - succeeded by `PyPy`)

#### Frozon Binaries
* How does Python program generate standalone binary executables
* Frozen binaries bundle byte code of program files, PVM, and any dependencies into a single package. 
* Ex. py2exe, py2app, freeze, cx_freeze, etc
* not same as output of a true compiler. It runs byte code through a virtual machine and run at the same speed as the original source files. Not particularly small, but not that big either.