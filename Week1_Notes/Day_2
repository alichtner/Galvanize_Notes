### Week 1 Day 2
# Object Oriented Programming

## Objectives
- Define Object-Oriented concepts
- Use OO in programs
- Instantiate objects
- Design and Implement a basic class
- List key magic methods
- State what a decorator is
- Use TDD (test-driven development) & PDB (python debugger) to verify code

## To-Dos
- look up the `super` function
- install `setup.sh`
- Google Ben Skrainka - Correctness in Data Science

## Functions of the day

- creates an ipython instance where inline plotting can be done and isn't an ipython notebook. This is where you can use seaborn.
  - `ipython qtconsole --matplotlib inline -m example_plots`
  ```python
    %matplotlib inline

    import numpy as np
    import pandas as pd
    from scipy import stats, integrate
    import matplotlib.pyplot as plt
    import seaborn as sns

    sns.set(color_codes=True)
    np.random.seed(sum(map(ord, "distributions")))
    ```

## Requirements for the course
- attendence - 9 excused allowed, 2 unexcused = nasty letter from registrar, 20+ minutes late is a partial unexcused, 3 partials = 1 full unexcused absence
- technical
- outcomes
- capstone

## Notes

- *Effective Python* is a good simple book
- OOP was developed to deal with large, distributed projects
- build with the idea of software reuse in mind
  - you can save time and make the code more bulletproof and maintainable

  ### Science is inherently linear:
   - Projects tend to build a pipeline
     1. Load data
     2. Compute something
     3. Serialize result to disk
    - this is nice because you can intervene in certain steps to do different oprations
    - You still need to know OOP though.
- The interface (command line) is a contract. You provide something, if what you provide meets the contract, the program will provide a services (output)
- **Class** - a user-defined type, on par with `float`, `str`, etc.
  - consists of
    - attributes (data fields)
    - methods (operations you can perform on the object)
- **Object** - is an instance of a class, and you can support multiple instances of the same class

```python
class Stooge(object):
    pass

larry = Stooge("Larry")
moe = Stooge("Moe")

moe.whoami() # method run on the instance of the Stooge object, 'moe'
```

`@property` - is a decorator

### 3 Main Concepts of OO
1. **Encapsulation** - forces code to manipulate an object's internal state only through method calls:
    - this is another way of saying, don't alter object's externally `larry.name = 'fred'` is bad, `self.name = name` is good
    - Python will not force encapsulation, we have to watch ourselves
2. **Inheritance** - derive a child class from a base class
    - Allows for specialization to be built onto an already built class
    - gets all the functionality of the Base class for free
    - Child methods override Base methods of the same name
3. **Polymorphism** - Treat multiple objects from different classes with the same interface
    - usually this involves instantiating classes with a common base class
    - Python uses duck-typing:
       - "if it looks like a duck and quacks like a duck, it's a duck"

### Public vs. Protected vs. Private
- Public: accessible by any external code
- Protected: access depends on the language
- Private: accessible only be code from the same class, but not derived classes
  - In Python, start the name with '_' if it is private
  - This doesn't actually restrict people from using it, it just signifies that it shouldn't be changed, it's a signal

### Very basic OOP Design
- Decompose your problem into nouns and verbs
  - noun - implement as a class
  - verb - implement as a method

 - Composition / Aggregation
   - Class contains an object of a class with the desired functionality
   - Often, just basic types: str, float, list, dict...
   - Has-a = aggregation
- Inheritance
   - Class specializes behavior of a base class
   - Is-a = use inheritance
- Make sure your interface is intuitive and friction-free
   - Use unit test or specification test
     - to verify interface is good before implementation
     - to exercise individual functions or objects before application is complete
   - Stub out methods using `pass`

```python
class FancyRegression(object):
    def __init__(self):
        pass

    def fit(self, X, y):
        pass
```

### Separations of Concern (SoC)
- Try to keep 'concerns' separate:
  - use different layers of concern
  - A concern is a set of information of a resource

### Core OOP in python
- Use `class` keyword
- Always derive your class from object
- Capitalize name of each class (no underscores)
- Using ''' text ''' right after the method definition is the docstring that will print when method? is called
- `self` is how you refer to the instances' own data

## Advanced OOP
- `*args` and `**kwargs`
  - shorthand to refer to a variable number of arguments
  - for regular argument, use `*args`
    - `*args` is a list
    - `**kwargs` is a dictionary - these are named variables

**Case 1**
```python
def myargs(arg1, arg2, arg3):
    return arg1 * arg2 * arg3

z = [2,3,4]
myargs(*z)
```

**Case 2**
```python
def args2list(*args):
    return [ix for ix in args]

args2list(1, 2, 3, 4)
[1, 2, 3, 4]]
```

## Static Methods
- these are normal functions which live in a class's namespace

## Add magic methods to your class

## Decorators (@)
Are things that you can add to your functions to give them additional behaviors
- @property - often with ``@<NameOfProperty>``
- @classmethod
- @staticmethod
- @abstractmethod

## Unit test! and Debugger! Do it!
- `%pdb` - in ipython, turns the debugger on, turn it off with the same command
- `import pdb.set_trace()`
- move up and down in the `stack frame` using `u` and `d`, this will allow you to look at how the functions are running when they are chained into one another
- `s` excecutes the next line
- `c` continues execution until a break point `b` is reached
