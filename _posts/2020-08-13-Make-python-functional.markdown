---
layout : post
---
<https://towardsdatascience.com/how-to-make-your-python-code-more-functional-b82dad274707>

Here is an article instroduced how to make a python code more functional.

- Make a simple function call
'''
def f(a, b):
  return a + b
'''

- Make a simple funcation with a function as a argument
'''
def f(g):
  g()
'''

- Make a simple function return a function
'''
def f:
  def g(a, b):
    return a+b
  return g
'''

- Combine
'''
def f(k):
  def g(a, b):
    k()
    return a+b
  return g
'''

- List comprehension
'''
l = [x**2 for x in range(5)]
l = [x**2 for x in range(5) if x % 2 == 0]
'''

- Generator which is used for big objects list
'''
g = (x ** 2 for x in range(10000))
next(g) #0
next(g) #1
next(g) #2
[next(g) for x in range(10)]
'''

- Built-in function in python

-- map()
map return a generator
'''
sq = list(map(lambda x : x ** 2, [0,1,2,3])) #[0, 1, 4, 9]
'''

-- filter()
'''
a = list(filter(lambda x: x%2 == 0, [0, 1, 2, 3])) #[0, 4]
'''

-- enumerate() for get pair of index
'''
# Print out list pair of index and value
for n in enumerate([0, 1, 2, 3]) :
  print(n)
'''

-- zip()
'''
list(zip(['a','b','c'],[1,2,3]))
'''
