Created: 2025-01-03 12:46
Tags: #unpacking #sequence #iterable #indexes #error_prone #value_swapping #parallel_assignment #argument_prefixing #nested

**Unpacking vs Using indexes**
Unpacking is important because it avoids unnecessary and error-prone use of indexes to extract elements from sequences.
Also, unpacking works with any iterable object as the data source—including iterators which don’t support index notation [].

**Different Types of unpacking**
1. parallel assignment: assigning items from an iterable to a tuple of variables
```
>>> lax_coordinates = (33.9425, -118.408056)
>>> latitude, longitude = lax_coordinates # unpacking
>>> latitude
33.9425
>>> longitude
-118.408056
```
2. swapping value:
```
>>> b, a = a, b
```
3. prefixing an argument with * when calling a function
```
>>> divmod(20, 8)
(2, 4)
>>> t = (20, 8)
>>> divmod(*t)
(2, 4)
>>> quotient, remainder = divmod(*t)
>>> quotient, remainder
(2, 4)
```
4. allowing functions to return multiple values in a way that is convenient to the caller.
```
>>> import os
>>> _, filename = os.path.split('/home/luciano/.ssh/id_rsa.pub')
>>> filename
'id_rsa.pub'
```
5. Using `*` to grab excess items: Defining function parameters with *args to grab arbitrary excess arguments is a classic Python feature. In Python 3, this idea was extended to apply to parallel assignment as well
```
>>> a, b, *rest = range(5)
>>> a, b, rest
(0, 1, [2, 3, 4])
>>> a, b, *rest = range(3)
>>> a, b, rest
(0, 1, [2])
>>> a, b, *rest = range(2)
>>> a, b, rest
(0, 1, [])
```

6. Unpacking with * in function calls and sequence literals: In function calls, we can use * multiple times
```
>>> def fun(a, b, c, d, *rest):
... return a, b, c, d, rest
...
>>> fun(*[1, 2], 3, *range(4, 7))
(1, 2, 3, 4, (5, 6))
```

   The * can also be used when defining list, tuple, or set literals, as shown these examples
```
>>> *range(4), 4
(0, 1, 2, 3, 4)
>>> [*range(4), 4]
[0, 1, 2, 3, 4]
>>> {*range(4), 4, *(5, 6, 7)}
{0, 1, 2, 3, 4, 5, 6, 7}
```
7. Nested Unpacking: The target of an unpacking can use nesting, e.g. (a, b, (c, d)).Python will do the right thing if the value has the same nesting structure.
```
metro_areas = [
('Tokyo', 'JP', 36.933, (35.689722, 139.691667)),
('Delhi NCR', 'IN', 21.935, (28.613889, 77.208889)),
('Mexico City', 'MX', 20.142, (19.433333, -99.133333)),
('New York-Newark', 'US', 20.104, (40.808611, -74.020386)),
('São Paulo', 'BR', 19.649, (-23.547778, -46.635833)),
]
def main():
print(f'{"":15} | {"latitude":>9} | {"longitude":>9}')
for name, _, _, (lat, lon) in metro_areas:
if lon <= 0:
print(f'{name:15} | {lat:9.4f} | {lon:9.4f}')
if __name__ == '__main__':
main()
```


## References 
1. [[An Array of Sequences]]