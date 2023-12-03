---
layout: post
title: you're going to love dis

description:
summary:
tags: [python]
---

I always used to wonder how python is interpreted and how does it exactly work under the hood during my journey of learning Python.
As Python is an interpreted language, I was wondered how this the interpretation works under the hood.

> The best practice is to reverse engineer the problem to its component parts. This is going to take it to the byte level.

The dis module supports the analysis of `CPython` bytecode by disassembling it, with the help of `dis` you can see what byte level operations are being done by your code.
<br/><br/>

Enough details, let's see it in action. I made a `foo.py` file with a very trivial function for showcasing.

```python3
import dis
def run(x: int) -> int:
    return x + 1

if __name__ == "__main__":
    dis.dis(run)
```

```bash
>> python foo.py
 4   0 LOAD_FAST                0 (x)
     2 LOAD_CONST               1 (1)
     4 BINARY_ADD
     6 RETURN_VALUE
```
`LOAD_FAST`: is used for local variables, accessing the value in an array by index <br/>
`LOAD_CONST`: instruction is used to load a constant onto the stack <br/>
`BINARY_ADD` : is used to add the two values <br/>
`RETURN_VALUE` : is used to return this value from the function <br/>
