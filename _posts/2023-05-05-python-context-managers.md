---
layout: post
title: wait, you use context-managers?
description:
summary:
img:
tags: [python, tech, work]
---

![memory-leak](/assets/hard_reboot.png)

_Memory leaks?! pfft! my good ol’ Python handles everything for me_. Well, we all wish this could have been true, but that’s not the case. Before getting to know `context managers`, let me highlight the usage of `with` statement. Let’s see it with the help of a code.

```python
with open('sample.txt', 'w') as file:
    file.write('blah')
```

but what if deadlines are near and you're throwing the most complex macros at your code to make that deadline possible and exploit Python with a poor choice of code like

```python
file = open('sample.txt')
file.write('blah')
file.close()
```

_Looks good? let's move on with life and wait for that appraisal?_ <br/> <br/>
If you are also thinking like that then you're in the wrong. There are few but major things that you overlooked that can shoot you in the feet,
what if `file.write()` runs into an error and never reaches `file.close()`? and that's how a memory leak is produced because you can never go back to that piece of run because it failed in execution.

Let me break the above code into verbose way of Python and *the* correct way.

```python
file = open('sample.txt')
try:
    file.write('blah')
finally:
    file.close()
```
Now we got the big guns, our near and dear `try-catch` statements which will help us deal with exceptions and how to handle them and that is the exact way how `with` statement works under the hood.

Now we shall proceed with `context-managers` and how we can make our own _class-based_ or _function-based_ `with` statements.
To do so all we need is to add `__enter__` & `__exit__` dunder methods.

#### class-based
```python
class Manager:
    def __init__(self, name):
        self.name = name

    def __enter__(self):
        self.file = open(self.name, 'w')
        return self.file

    def __exit__(self, exc_type, exc_val, exc_tb):
        if self.file:
            self.file.close()

$ usage:

with Manager('sample.txt') as f:
    f.write('blah')
```


#### function-based
```python
from contextlib import contextmanager

@contextmanager
def manage_file(name: str):
    try:
        file = open(name, 'w')
    finally:
        file.close()

$ usage:

with manage_file('sample.txt') as file:
    file.write('blah')

```

and that's how we make our own `context-manager` from scratch.
<br/> <br/>
_until next time. :)_
