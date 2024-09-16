## In Short: It Makes Importing Python Modules Faster[](https://realpython.com/python-pycache/#in-short-it-makes-importing-python-modules-faster "Permanent link")

Even though Python is an [interpreted programming language](https://en.wikipedia.org/wiki/Interpreter_(computing)), its interpreter doesn’t operate directly on your Python code, which would be very slow. Instead, when you [run a Python script](https://realpython.com/run-python-scripts/) or [import](https://realpython.com/python-import/) a Python module, the interpreter compiles your high-level Python source code into [bytecode](https://en.wikipedia.org/wiki/Bytecode), which is an intermediate binary representation of the code.

This bytecode enables the interpreter to skip recurring steps, such as [lexing and parsing](https://realpython.com/cpython-source-code-guide/#lexing-and-parsing) the code into an [abstract syntax tree](https://en.wikipedia.org/wiki/Abstract_syntax_tree) and validating its correctness every time you run the same program. As long as the underlying source code hasn’t changed, Python can reuse the [intermediate representation](https://en.wikipedia.org/wiki/Intermediate_representation), which is immediately ready for execution. This saves time, speeding up your script’s startup time.

Python uses local `__pycache__` folders to store the compiled bytecode of **imported modules** in your project. On subsequent runs, the interpreter will try to load precompiled versions of modules from these folders, provided they’re up-to-date with the corresponding source files. Note that this [caching](https://realpython.com/lru-cache-python/) mechanism only gets triggered for modules you _import_ in your code rather than executing as scripts in the terminal.

In addition to this **on-disk bytecode caching**, Python keeps an **in-memory cache of modules**, which you can access through the [`sys.modules`](https://docs.python.org/3/library/sys.html#sys.modules) dictionary. It ensures that when you import the same module multiple times from different places within your program, Python will use the already imported module without needing to reload or recompile it. Both mechanisms work together to reduce the overhead of importing Python modules.

Next, you’re going to find out exactly how much faster Python loads the cached bytecode as opposed to compiling the source code on the fly when you import a module.
```
project/
│
├── mathematics/
│   │
│   ├── __pycache__/
│   │
│   ├── arithmetic/
│   │   ├── __init__.py
│   │   ├── add.py
│   │   └── sub.py
│   │
│   ├── geometry/
│   │   │
│   │   ├── __pycache__/
│   │   │
│   │   ├── __init__.py
│   │   └── shapes.py
│   │
│   └── __init__.py
│
└── calculator.py
```

```shell
$ python -X importtime calculator.py
(...)
import time:     20092 |      20092 | arithmetic

$ python -X importtime calculator.py
(...)
import time:       232 |        232 | arithmetic

$ python -X importtime calculator.py
(...)
import time:       203 |        203 | arithmetic
```