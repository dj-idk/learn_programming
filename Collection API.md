The goal of this brief section is to give a panoramic view of Python’s most important collection interfaces, showing how they are built from special methods.

ABCs: Abstract Base Classes

The Collection
ABC (new in Python 3.6) unifies the three essential interfaces that every collection should implement:

```
Iterable to support for, unpacking, and other forms of
iteration;
Sized to support the len built-in function;
Contains to support the in operator.
```
Python does not require concrete classes to actually inherit from any of these ABCs. ==Any class that implements __len__ satisfies the Sized interface.==
Three very important specializations of Collection are:
```
Sequence, formalizing the interface of built-ins like list and str;
Mapping, implemented by dict,
collections.defaultdict, etc.;
Set: the interface of the set and frozenset built-in types.
```

Only Sequence is Reversible, because sequences support arbitrary ordering of their contents, while mappings and sets do not.
Created: 2025-01-03 11:14
Tags: #ABC

## References 
1. [[Core Python]]