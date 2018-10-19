## async programming with coroutines

There are two ways to get the result of a coroutine .
1) By using await
2) By adding it to the event loop.


## dafaq is event loop
Evvent loop is responsible for executing asynchronous code.It decides when to switch from one coroutine to another.
we can add mulitple coroutines to the evenet loop.

this exposes two apis to run coorutines concurrenlt .
1) run_until_complete()
2) run_forever()

When a task is created from a async function and submittesd the event loop , we get Futures in return, which is just a placeholder value.There are two apis to consider again

* `loop.create_task(coro)`
* `loop.ensure_future(coro)`

loop.create_task(coro) return a Task object which is a subtype of future object.

## lets see a example

```python

import asyncio
async def foo():
  print('i am foo'):
  
loop = asyncio.new_event_loop()

task1 = loop.create_task(foo())
task2 = loop.create_task(foo())
loop.run_until_complete(asyncio.wait([task1, task2]))

print (task1.result())
print (task2.result())

```

steps:

* deinfe your async function
* async function return coroutines
* coroutines needs to be scheduled, so
* create an event loop
* create tasks from coroutines
* add tasks to the event loop
* wait for tasks to get cimpleted
* get the results back using `task.result()`
