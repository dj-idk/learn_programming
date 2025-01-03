Created: 2025-01-03 13:53
Tags: #slicing #sequence #list #tuple #str #step 

**Why Slices and Range Exclude the Last Item**
It's more convenient because:
1. It’s easy to see the length of a slice or range when only the stop position is given:` range(3) and my_list[:3]` both produce three items.
2. It’s easy to compute the length of a slice or range when start and stop are given: just subtract stop - start.
3. It’s easy to split a sequence in two parts at any index x, without overlapping: simply get` my_list[:x] and my_list[x:]`.
```
>>> l = [10, 20, 30, 40, 50, 60]
>>> l[:2] # split at 2
[10, 20]
>>> l[2:]
[30, 40, 50, 60]
>>> l[:3] # split at 3
[10, 20, 30]
>>> l[3:]
[40, 50, 60]
```

**Slice Objects**
This is no secret, but worth repeating just in case: `s[a:b:c]` can be used to specify a stride or step c, causing the resulting slice to skip items.(`seq[start:stop:step]`) 

```
Example 2-12. Line items from a flat-file invoice
>>> invoice = """
...
0.....6.................................40........52...55........
... 1909 Pimoroni PiBrella $17.50 3
$52.50
... 1489 6mm Tactile Switch x20 $4.95 2
$9.90
... 1510 Panavise Jr. - PV-201 $28.00 1
$28.00
... 1601 PiTFT Mini Kit 320x240 $34.95 1
$34.95
... """
>>> SKU = slice(0, 6)
>>> DESCRIPTION = slice(6, 40)
>>> UNIT_PRICE = slice(40, 52)
>>> QUANTITY = slice(52, 55)
>>> ITEM_TOTAL = slice(55, None)
>>> line_items = invoice.split('\n')[2:]
>>> for item in line_items:
... print(item[UNIT_PRICE], item[DESCRIPTION])
...
$17.50 Pimoroni PiBrella
$4.95 6mm Tactile Switch x20
$28.00 Panavise Jr. - PV-201
$34.95 PiTFT Mini Kit 320x240
```


## References 
1. [[An Array of Sequences]]