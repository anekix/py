## Generators 
* clean way to create custom iterators
* allows function to have state.
* uses `yield` expression to return excecution controll back to the caller


```python

def generator():
   print ('hello')
   yield
   print ('world')
   yield
```

* Calling above generator will not call the function , it will return a `generator object`
* To iterate on the generator use `next()` method( remeber just like creating a  custom iterator? but in a clean way.)
* When there is no more element to iterate a `StopIteration` exception is raised
   
   ## Generator Expressions
   
   Same as lambda function creates an anonymous function, generator expression creates an anonymous generator function.
 ```python
 my_list = [1, 3, 6, 10]
(x**2 for x in my_list)
 # Output: <generator object <genexpr> at 0x0000000002EBDAF8>
```
