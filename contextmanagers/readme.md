## Context Managers are used to manage resources in python
considering opening a file in your program. Now every process has a limited no of files that can be opened at  agiven time, which is limmited by the OS.

```python
files = []
for i in range(1000000):
  files.append( open('i.txt','w'))
```
you will get an error that looks something like this `IOError: [Errno 24] Too many open files: 'ff.txt'`
it happens when we forget to close **opened** files.

Many times we might miss closing up the opened files. this might also happen when a file is opened inside a function and some exception is thrown before `close()` is called. we end up with leaking file handlers.

One solution would be to use `try/except/finally` statements , but luckily we have another & much cleaner solution.

## ENTER CONTEXT MANAGERS................
The syntax is

```python

with something_returning_context_manager() as resource_name:
  # do something with the resource
```

ex.

```python
with open('file.txt') as f:
  content = f.read()
```

## CREATING CUSTOM CONTEXT MANAGERS
The simplest way is to create a class:
* That has a `__enter__()` method defined(return the resource that has to be managed)
* That has a `__exit__()` method defined(does the cleanup work)

Ex.

```python

class File:
  def __init__(self, filename):
      self.file = filename
  
  def __enter__(self):
      self.f = open(file)
      return self.f
      
  def __exit__(self):
      self.f.close()
      
```

use it as 
```python
with File('sanam.txt') as f:
    content = f.read()
```

```python
f = open('file.txt')
for line in f:
  ## some processing with the file
```
  
