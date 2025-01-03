Created: 2025-01-03 13:16
Tags: #pattern #sequence #match/case #switch/case #unpacking #destructuring #scala #elixir #pattern_matching

**match/case vs. switch/case**

On the surface, match/case may look like a the switch/case
statement from the C language—but that’s only half the story. One key improvement of match over switch is destructuring—a more advanced form of unpacking. Destructuring is a new word in the Python vocabulary, but it is commonly used in the documentation of languages that support pattern matching—like Scala and Elixir.

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
for record in metro_areas:
match record:
case [name, _, _, (lat, lon)] if lon <= 0:
print(f'{name:15} | {lat:9.4f} | {lon:9.4f}')
```

> [!NOTE] _ Symbol In Sequence Pattern
> The _ symbol is special in patterns: ==it matches any single item in that position, but it is never bound to the value of the matched item.== Also, the _ is the only variable that can appear more than once in pattern—unless the pattern is a combination of patterns joined by the | operator (which also has special meaning in a case clause).


Sequence Patterns
1. Sequence patterns may be written as tuples or lists or any combination of nested tuples and lists, but it makes no difference which syntax you use: in a pattern, tuples and lists match any sequence.
2. In the standard library, these types are compatible with sequence patterns: `list memoryview array.array tuple range collections.deque`
3. A sequence pattern can be more strict using type information.

## References 
1. [[An Array of Sequences]]