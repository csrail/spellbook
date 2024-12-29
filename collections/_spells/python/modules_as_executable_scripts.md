---
layout: spell
date: 28-12-2024
---

Beyond importing modules, python files can be turned into executable scripts by adding the following code to the end of your module:

```python
if __name__ == "__main__":
    # import sys to access to command line arguments
    import sys
    # f function from module is applied onto command line argument
    f(sys.argv[1])
```

When passing a python file as an argument to the python interpreter, the `__name__` of the python module becomes `__main__` resulting in the code being executed as though the module was a script.

```python
python module.py <arguments>
```

When importing the module, the script isn't executed.

```python
import module
```
