
## Week 1 Day 1
---
## Objectives
- Setup Computer
- Install / Config
- Typical Workflow
- Review Python
  - Writing efficient code
  - correctness
---
#### Random Notes
- CRISP_DM
  - the industry standard for data science
- pdb - python debugger (a must-learn tool)
  - %pdb in ipython
-     __iter__ - # is pronounced "dunder-iter"

#### Functions of the Day

- **id()** - gives memory id of an object in python
- **yield** - can be used to create generators
- **operation.itemgetter()** -
- **pep8** <python file> - run from the command line, this will check for proper formatting

## Notes
- Don't do forecasting in Python, use R
- Python is interpreted - makes it easy to prototype and explore
- [Lecture Slides](https://github.com/zipfian/DSI_Lectures/blob/master/python-intro/ben_skrainka/bss-lecture.pdf)
- Install Galvanize Stack using [setup.sh](https://github.com/alichtner/welcome) from the welcome repo
- Unix works on a *filters + pipes* paradigm: '|' = pipe
- try to learn VI(M)

### Unix Commands
| Command | Action |
| --|--|
|pwd | Display current directory |
|ack|Recursively search files in a tree for an RE pattern|
|grep|Search for a pattern in a file|
|which|Determine version of a command which is accessible|
|wc|Count characters, words, lines|
|less|Page through a file|
|head/tail|look at start or end of file|

- To write good code you need to run a tight feedback loop

### Unit Testing
- these are mini-tests which run functions of the code you are trying to develop so you know your individual functions are working
- **Unit Test** everything you can:
  - fastest way to develop code
  - High quality way to develop code
  - Unit test framework will setup and teardown fixtures
  - Use RED/GREEN/GREEN (also called Test-Driven Development - TDD)
     - red - write unit test first; check that it fails
     - green - implement code which passes unit test
     - green - refactor code to work better

- Read more well-written code
- Prefer **DRY** (do-not-repeat-yourself) to **WET** (we-enjoy-typing) coding

---
# Python Essentials
- good programmers are lazy
- start by listing requirements and/or writing a spec
    - ex. INPUT/OUTPUT
- simplify complex by problems by 'divide and conquer'
- decompose problem into functions
  - each function should do one thing and do it well
- Different Styles: Structured programming / Top down / Bottom up / OOP

### Scope: LEGB
Questions of scope are resolved in LEGB
- local
- enclosing
- global
- built-in

### Shallow vs. Deep Copy
```python
list2 = my_list # creates a reference to an object

import copy # Make a deep copy
my_clone = copy.deepcopy(my_list)
```

- prefer itertools.izip() to zip(), this zips together multiple lists and acts as a generator

```python
from collections import defaultdict

def anagram(lst):
    result = []
    new_d = defaultdict(list)
    for word in lst:
        d[tuple(sorted(word))].append(word)
    for k, v in d.iteritems():
        if len(value) > 1:
            result.extend(value)
    return result
```

### Generator Comprehension

- make a list comprehension and replace [] with (), now it's a generator, uses less memory and is faster
