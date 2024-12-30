Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python 
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# pprint
Contains:
- `pprint()`
- `pformat()` 
that will "pretty print" a dictionary's values.

```python
import pprint
message = 'It was a  bright cold day in April, and the clocks were striking thirteen.'
count = {}

for character in message:
	count.setdefault(character, 0)
	count[character] = count[character] + 1

pprint.pprint(count)
```

## String instead of Display
Obtain prettified text as `string` instead of displaying it on the screen, call `pprint.pfomat()`
```python
pprint.pprint(someDictionaryValue)
print(pprint.pformat(someDictionaryValue))
```

