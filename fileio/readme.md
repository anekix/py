
## open  file in read mode

```python
f = open('filenmae.txt')
```

## loop over lines in file:

```python
for line in f:
  print (line)
```
## load content of file in memory at once


```python
f = open('filename.txt')
content = f.read()
```

## load contents of file in memory as array


```python
f= open('filename.txt')
array_content = f.readlines()
```

## proper way to open file in 


```python

try:
  f = open('filename.txt')
except Exception as e:
  print str(e)
  
with f:
  for line in f:
    print(line)
```


