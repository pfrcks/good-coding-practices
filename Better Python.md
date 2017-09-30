
_Programs must be written for people to read, and only incidentally for machines to execute._

—Abelson & Sussman, Structure and Interpretation of Computer Programs

* [Code Like a Pythonista](http://python.net/~goodger/projects/pycon/2007/idiomatic/handout.html)
* [Python Anti-Patterns](http://python.net/~goodger/projects/pycon/2007/idiomatic/handout.html)

# Learnings

#### Comma is the tuple constructor, not the paranthesis


```python
1,
```




    (1,)




```python
(1,)
```




    (1,)




```python
value = 1,
value
```




    (1,)



#### "_" stores the last printed expression


```python
1+1
```




    2




```python
_
```




    2



#### Dictionary `get` method.

Instead of checking whether a key is present in a dictionary use:

`dict.get(key, defualtvaluetobeassignedifkeydoesnotexist)`

#### Building dictionary from two lists


```python
given = ['John', 'Eric', 'Terry', 'Michael']
family = ['Cleese', 'Idle', 'Gilliam', 'Palin']

pythons = dict(zip(given, family))
```


```python
print pythons
```

    {'John': 'Cleese', 'Michael': 'Palin', 'Eric': 'Idle', 'Terry': 'Gilliam'}


#### Names in Python

`a=1`

we are assigning the name `a` to the object `1`

#### Default Parameter Values


```python
def bad_append(new_item, a_list=[]):
    a_list.append(new_item)
    return a_list
```


```python
print bad_append('one')
```

    ['one']



```python
print bad_append('two')
```

    ['one', 'two']


The problem here is that the default value of a_list, an empty list, is evaluated at function definition time. So every time you call the function, you get the *same default value*.

To avoid this use `a_list=None`

#### Generator Expressions

Generator Expressions are like List Comprehensions except they are lazzzzzzzzzzzzzzyyyyyyyyyyyyyyy. 

Use List Comprehension when computed list is desired end result. If computed list is just an intermediate step use generator expression.

#### yield keyword

The `yield` keyword turns a function into a generator. When you call a generator function, instead of running the code immediately Python returns a generator object, which is an iterator; it has a next method. for loops just call the next method on the iterator, until a StopIteration exception is raised. You can raise StopIteration explicitly, or implicitly by falling off the end of the generator code as above.

#### Module Structure
"""module docstring"""

imports
constants
exception classes
interface functions
classes
internal functions & classes

def main(...):
    ...

if \_\_name\_\_ == '\_\_main\_\_':
    status = main()
    sys.exit(status)

```python

```
