Created: 2025-01-03 12:16
Tags: #tuple #records #dummy_variable #unpacking

Tuples hold records: each item in the tuple holds the data for one field and the position of the item gives its meaning.

```
Example 2-7. Tuples used as records
>>> lax_coordinates = (33.9425, -118.408056)
>>> city, year, pop, chg, area = ('Tokyo', 2003, 32_450, 0.66,
8014)
>>> traveler_ids = [('USA', '31195855'), ('BRA', 'CE342567'),
... ('ESP', 'XDA205856')]
>>> for passport in sorted(traveler_ids):
... print('%s/%s' % passport)
...
BRA/CE342567
ESP/XDA205856
USA/31195855
>>> for country, _ in traveler_ids:
... print(country)
...
USA
BRA
ESP

The % formatting operator understands tuples and treats each item as a separate field.
The for loop knows how to retrieve the items of a tuple separately— this is called “unpacking.” Here we are not interested in the second item, so we assign it to _, a dummy variable.
```

> [!NOTE] Dummy Variable
> In general, using _ as a dummy variable is just a convention. It’s just a strange but valid variable name. However, there are two contexts where _ is special: 1. In the Python console, the result of executing a line is assigned to _—unless the result is None. 2. In a match/case statement, _ is a wildcard that matches any value but is never assigned a value.

**Why you should used to tuples for records**
there’s no need to go through the trouble of creating a class just to name the fields, especially if you leverage unpacking and avoid using indexes to access the fields.


## References 
1. [[An Array of Sequences]]