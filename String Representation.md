The __repr__ special method is called by the repr built-in to get the string representation of the object for inspection. Without a custom__repr__, Python’s console would display a Vector instance <Vector object at 0x10e100070>.

```
TIP
Programmers with prior experience in languages with a toString method tend to
implement __str__ and not __repr__. If you only implement one of these special
methods in Python, choose __repr__.
```
Created: 2025-01-03 10:56
Tags: #special_method 

## References 
1. [[Special Methods]]