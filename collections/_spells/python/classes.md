---
layout: spell
date: 28-12-2024
---

Reading Class definitions
```python
# class definition with type-hinting
class Current(Inherited):
    """ One line summary for Class Definition

    Multi-line description.
    Detailed documentation to describe class usage.

    """

    # private instance variables with type hints
    _a: type1 | type2 = type2
    _b: int | None = None

    # __init__ is the constructor function
    def __init__(self,
                 param1: type1 | type2 = type2, # parameters have type hints
                 param2: int | None = None) -> None: # constructor function returns nothing
                 """One line summary for constructor function.

                 Multi-line description.
                 Detailed documentation to describe constructor function.

                 """

                 # assignment of arguments to private variables
                 self._a = param1
                 self._b = param2
```