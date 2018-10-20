## what are iterators

An **iterator** is an object which can be iterated upon. **iterators** are returned by **iterables** examples of inbuilt iterables which return iterables are list, dicts, tuples etc.
For an object to be an iterator it must implement **iterator protocol**.

##Iteratpr protocol

for an object to become an iterator it must implement the following methods
* `__iter__()`
* `__next__()`


## examples of inbuilt iterable objects are list, tuples...etc

they are iterable containers from which we can get an iterator using `iter(iterable_object)`.once we have an iterator we can get the next elemet of the container using `next(iterator_object)` method.when all the elements of a container have been exhausted a `StopIterator` exception is raised.

one of the inbuilt way of loping on an `iterable object` is by using `for` construct.

what inbuilt `for` does is , 
* it calls the `iter(iterbale_object)` implicitly, which return an `iterator`.
* it uses the `next()` method on the `iterator` returned to get the next element.
* it stops when a `StopIteration` is raised.

## In short 

An **iterable** is an object from whch we can get an **ietrator**
Whenever you use a for loop, or map, or a list comprehension, etc. in Python, the **next()** method is called automatically to get each item from the iterator, thus going through the process of iteration.




