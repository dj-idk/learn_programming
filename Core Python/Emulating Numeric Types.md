Created: 2025-01-03 10:42
Tags: #special_method

Several special methods allow user objects to respond to operators such as +.

```
import math
class Vector:
def __init__(self, x=0, y=0):
self.x = x
self.y = y
def __repr__(self):
return f'Vector({self.x!r}, {self.y!r})'
def __abs__(self):
return math.hypot(self.x, self.y)
def __bool__(self):
return bool(abs(self))
def __add__(self, other):
x = self.x + other.x
y = self.y + other.y
return Vector(x, y)
def __mul__(self, scalar):
return Vector(self.x * scalar, self.y * scalar)
```
Note that the f-string in our __repr__, uses !r to get the standard representation of the attributes to be displayed. This is good practice, because it shows the crucial difference between Vector(1, 2) and Vector('1', '2')
## References 
1. [[Special Methods]]