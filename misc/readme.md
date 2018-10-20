## sort a given list of dictionaries using a key value
```python 
l  = [
 {'name':'rosh' ,  'age':22},
 {'name':'jane' ,  'age':20},
 {'name':'aron' ,  'age':21},
 {'name':'dave' ,  'age':23},
]
```
```python
sorted(l, key=lambda x:x['age'])
```
OR
```python
from operator import itemgetter
sorted(l, key=itemgetter('age'))
```
