Created: 2025-01-03 12:34
Tags: #tuple #list #immutable #clarity #performance #bug #mutable 

**Benefits of leveraging tuple's immutability**
1. Clarity: when you see a tuple in code, you know its length will never change.
2. Performance: a tuple uses less memory than a list of the same length, and they allow Python to do some optimizations.

**Scope of immutability**
Be aware that the immutability of a tuple only applies to the references contained in it. References in a tuple cannot be deleted or replaced. But if one of those references points to a mutable object, and that object is changed, then the value of the tuple changes.

```
>>> a = (10, 'alpha', [1, 2])
>>> b = (10, 'alpha', [1, 2])
>>> a == b
True
>>> b[-1].append(99)
>>> a == b
False
>>> b
(10, 'alpha', [1, 2, 99])
```

**Tuples with mutable items**
Tuples with mutable items can be a source of bugs. An object is only hashable if its value cannot ever change. An unhashable tuple cannot be inserted as a dict key, or a set element.

```
>>> def fixed(o):
... try:
... hash(o)
... except TypeError:
... return False
... return True
...
>>> tf = (10, 'alpha', (1, 2))
>>> tm = (10, 'alpha', [1, 2])
>>> fixed(tf)
True
>>> fixed(tm)
False
```


## References 
1. [[An Array of Sequences]]