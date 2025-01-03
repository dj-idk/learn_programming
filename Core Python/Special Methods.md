**Syntax: 
```
The special method names are always written with leading and trailing double underscores. For example, the syntax obj[key] is supported by the __getitem__ special method. In order to evaluate my_collection[key], the interpreter calls
my_collection.__getitem__(key).
```
**When Do we use them: 
We implement special methods when we want our objects to support and interact with fundamental language constructs such as:
Collections;
Attribute access;
Iteration (including asynchronous iteration using async for);
Operator overloading;
Function and method invocation;
String representation and formatting;
Asynchronous programing using await;
Object creation and destruction;
Managed contexts using the with or async with statements.

**Advantages:
- No need for memorizing arbitrary methods
- We don't need to reinvent the wheel

**Summary:
By implementing special methods, your objects can behave like the built-in types, enabling the expressive coding style the community considers Pythonic.

Table of content:
[[Emulating Numeric Types]]
[[String Representation]]
[[Boolean Value of a Custom Type]]
[[Collection API]]
[[Overview of Special Method]]

Tags: #special_method 

1. [[Core Python]]
