---
layout: post
title: wait, you use context-managers?
description:
summary:
img:
tags: [python, tech, work]
---

[![memory-leak](/assets/hard_reboot.png)](/assets/hard_reboot.png)

_Memory leaks?! pfft! my good ol' Python handles everything for me._ Well we wish we could've had it all  but that's not the case. Before getting to know `context-managers` let's learn the usage of `with` statement. Let's see it with a help of a code.

```python
with open('sample.txt', 'w') as file:
    file.write('Thanks Guido van Rossum')
```

but what if deadlines are near and you're throwing the most complex macros at your code to make that deadline possible and exploit Python with poor choice of code like

```python
file = open('sample.txt')
file.write('Thanks Guido van Rossum')
file.close()
```

_Looks good? let's move on with life and wait for that appraisal?_ <br/> <br/>
If you are also thinking like that then you're in the wrong. There are few but major things that you overlooked that can shoot you in the feet,
what if `file.write()` runs into an error and never reaches `file.close()`? and that's how a memory leak is produced because you can never go back to that piece of run because it failed in execution.

Let me break the above code into verbose way of Python and *the* correct way.

```python
file = open('sample.txt')
try:
    file.write('sweet text')
finally:
    file.close()
```
Now we got the big guns, our near and dear `try` catch statements which will help us deal with exceptions and how to handle it and that is the exact way how `with` statement works under the hood.
