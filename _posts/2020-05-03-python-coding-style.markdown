---
layout: post
title:  "Python-coding-style"
date:   2020-05-03 01:17:24 +0700
categories: jekyll update
---
After look up for coding convention for Python. I have read a few guide for python coding convention.

<https://docs.python-guide.org/writing/style/>
Firstly is coding style written by Hitchhiker.

In summary for tldr;

* Explicit code. Should write as normal thinking of people
* One state per line. As many languages convention, one line for one state
* Avoid magic wand. 
Avoid hacking (change the way object instantiated, created, change the way python import modules, embeded C into python).
We should avoid all of them, just keep the way straitforward as it is. That could reduce readibility, code analysis tool such as pylint,
pyflakes.
* We are all reponsible user.
In python there is many tricks. So we must be responsible.
* Returning value.
Keep single exit point is better. Should not return in the middle.
* PEP 8 for style check <https://www.python.org/dev/peps/pep-0008>
* PEP 20 for general guideline <https://www.python.org/dev/peps/pep-0020>

<https://www.geeksforgeeks.org/10-essential-python-tips-tricks-programmers>
<https://www.techbeamers.com/essential-python-tips-tricks-programmers>

1. swap
```
x, y = y, x
```
2. reverse a string
```
a = "abc"
print(a[::-1])
```
3. string concatenation
```
a = ["a", "b", "c"]
print("".join(a))
print(" ".join(a))
```
4. chaining of comparion
```
a = 10
print(1 < a <= 20)
print(1 > a <= 9)
```
5. know where is module located
```
import os
print(os)
```
6. enum in python
```
class A:
    E1, E2, E3 = range(3)
print(A.E1, A.E2, A.E3)
```

7. use dictionary for switch

```
stdcalc = {
	'sum': lambda x, y: x + y,
	'subtract': lambda x, y: x - y
}

print(stdcalc['sum'](9,3))
print(stdcalc['subtract'](9,3))

Output:
#1-> 12
#2-> 6
```

8. most frequent array

```
test = [1,2,3,4,2,2,3,1,4,4,4]
print(max(set(test), key=test.count))

#-> 4
```

9. reset recursion limit

```
import sys

x=1001
print(sys.getrecursionlimit())

sys.setrecursionlimit(x)
print(sys.getrecursionlimit())

#1-> 1000
#2-> 1001
```

10. check memory of object

```
import sys
x=1
print(sys.getsizeof(x))

#-> 24
```

11. use __slots__ to reduce memory overheads

```
import sys
class FileSystem(object):

	def __init__(self, files, folders, devices):
		self.files = files
		self.folders = folders
		self.devices = devices

print(sys.getsizeof( FileSystem ))

class FileSystem1(object):

	__slots__ = ['files', 'folders', 'devices']
	
	def __init__(self, files, folders, devices):
		self.files = files
		self.folders = folders
		self.devices = devices

print(sys.getsizeof( FileSystem1 ))

#In Python 3.5
#1-> 1016
#2-> 888
```

12. Search prefix or suffix 

```
print("http://www.google.com".startswith(("http://", "https://")))
print("http://www.google.co.uk".endswith((".com", ".co.uk")))

#1-> True
#2-> True
```

13. Switch case

```
def xswitch(x): 
	return xswitch._system_dict.get(x, None) 

xswitch._system_dict = {'files': 10, 'folders': 5, 'devices': 2}

print(xswitch('default'))
print(xswitch('devices'))

#1-> None
#2-> 2
```
14. Splash operator, \*-operator
https://docs.python.org/3/tutorial/controlflow.html#unpacking-argument-lists
```
x = [3,6]
print(list(range(*x)))
=> 3, 4, 5
```
```
def test(x, y, z):
	print(x, y, z)

testDict = {'x': 1, 'y': 2, 'z': 3} 
testList = [10, 20, 30]

test(*testDict)
test(**testDict)
test(*testList)

#1-> x y z
#2-> 1 2 3
#3-> 10 20 30
```
15. Create dictionary from two related sequences
```
a = [1, 2, 3]
b = [10, 20, 30]
print(dict(zip(a,b)))
```
16. Unify list from a complex list
```
import more_itertools
test = [[-1, -2], [1, 2, 3, [4, (5, [6, 7])]], (30, 40), [25, 35]]
print(list(more_itertools.collapse(test)))
#Output=> [-1, -2, 1, 2, 3, 4, 5, 6, 7, 30, 40, 25, 35]
```
17. * usage in python
https://medium.com/understand-the-python/understanding-the-asterisk-of-python-8b9daaa4a558
```
2 * 3
2 ** 3
zeros_list = [0] * 100
zeros_tuples = (0,) * 100
```

When use only positional arguments```print(*args)```
When use only keyword arguments```print(**key_word_args)```
When use both positional arguments and keyword arguments```print(*args,**key_word_args)```

Remaining in unpacking
```
alist = [1, 2, 3, 4, 5, 6]
*a, = alist #[1, 2, 3, 4, 5, 6]
*a, b, = alist #[1, 2, 3, 4, 5], 6
a, *b, c = alist # 1, [2, 3, 4, 5], 6
```

