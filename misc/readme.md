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

## NOTE:
the “value” of an immutable object can’t change, but it’s constituent objects can.
```python
l = [1,2,3]
obj = (l , 'hello')

l[0] = 99

print obj
# ([99,2,3], 'hello')

```

`obj` itself has no method to change its contents but the list object here can be changes & since its just a refrence that contents of the list will change inside the `obj`

## Mutable defaults argument (mistake)
if the argument is a mutable , its evalutaed once when the function is defined , not very time when the function is called.

```py
def foo(name, names=[]):
 names.append(name)
 print (names)

n = ['jack','sam','guoul']
for i in n:
 foo(i)
 
# output  
['jack']
['jack', 'sam']
['jack', 'sam', 'guoul']

```
To modify that:
```python
def foo(name,names=None):
 if not names:
  names = []
 names.append(name)
 print (names)



n = ['jack','sam','guoul']
for i in n:
 foo(i)
 
# output

['jack']
['sam']
['guoul']
```
