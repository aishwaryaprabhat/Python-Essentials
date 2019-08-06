
## Variables

A variable is basically a box in which you can store stuff (some value)
- 10variable = 10 not allowed
- &var = 10 not allowed
- var = 10
- var = 'some string'
- var = [1,2,3,4,5,6]


## Methods

A method is something that does something. Basically behaviours or actions in python programs are programmed as methods eg: print('something'). In this case print is the behaviour.


```python
myvar = 10
print(myvar)
```

    10


A new method is defined using the def keyword


```python
def my_print_method(): #naming conventions and restrictions same as variables
    print("Hello")
    print("World")
```

In the previous cell we have only created a method so nothing is actually printed out. We haven't called or run the method. Now we need to run the method.


```python
my_print_method()
```

    Hello
    World


Parameters are inputs to a method


```python
def my_print_method(parameter):
    print(parameter)
my_print_method("parameter")
```

    parameter


The "return" keyword represents what the function outputs or returns upon completing execution


```python
def my_method(num1, num2):
    return num1*num2

value = my_method(5,3)
print(value)
```

    15


## Lists, Tuples & Sets


```python
#List
grades = [80,85,90]
average_grade = sum(grades)/len(grades)
average_grade
```




    85.0




```python
grades.append(95)
grades
```




    [80, 85, 90, 95]




```python
#Assignment (only for lists)
grades[1] = 100
grades
```




    [80, 100, 90, 95]



### List Comprehension


```python
multiply_list = [x*3 for x in range(5)]
multiply_list
```




    [0, 3, 6, 9, 12]




```python
[n for n in range(100) if n%2==0]
```




    [0,
     2,
     4,
     6,
     8,
     10,
     12,
     14,
     16,
     18,
     20,
     22,
     24,
     26,
     28,
     30,
     32,
     34,
     36,
     38,
     40,
     42,
     44,
     46,
     48,
     50,
     52,
     54,
     56,
     58,
     60,
     62,
     64,
     66,
     68,
     70,
     72,
     74,
     76,
     78,
     80,
     82,
     84,
     86,
     88,
     90,
     92,
     94,
     96,
     98]



 ### Sets


```python
#Set is a collection of unique and unordered
grades_set = {111111,222,32,4456,77,88,99,99}
grades_set
```




    {32, 77, 88, 99, 222, 4456, 111111}




```python
grades_set.add(10101010)
```


```python
grades_set
```




    {32, 77, 88, 99, 222, 4456, 111111, 10101010}



### Set intersection, union and difference


```python
a = {1,2,3,4,5,6,7}
b = {2,4,6,8}
inter = a.intersection(b)
uni = a.union(b)
diff = a.difference(b) #what is in a that is not in b
print(inter,uni,diff)
```

    {2, 4, 6} {1, 2, 3, 4, 5, 6, 7, 8} {1, 3, 5, 7}


### Tuples


```python
#Tuples are immutable
tuple_grades = (1,2,3,4,5)
```


```python
tuple_grades = tuple_grades+(100,) #there has to be a , at the end if there is only one element
tuple_grades
```




    (1, 2, 3, 4, 5, 100)



## Loops


```python
my_string = "Aishwarya"

for character in my_string: #string is an iterable
    print(character)
```

    A
    i
    s
    h
    w
    a
    r
    y
    a



```python
count = 0
while count<10:
    print (count)
    count+=1
```

    0
    1
    2
    3
    4
    5
    6
    7
    8
    9


## If-else


```python
condition = False
if condition:
    print(condition)
else:
    print("Condition not true")
```

    Condition not true



```python
name = input("Enter your name: ")
```


```python
if name == 'Aish':
    print("Hi, Aish!")
else:
    print("Wrong person")
```

## Dictionaries

Dictionary, as opposed to a class, is cannot do operations on its own data


```python
my_dict = {'a':[1,2,3,4,5], 'b':[2,4,6,8]}
```

## Objects


```python
class LotteryPlayer():
    
    def __init__(self):
        self.name = "Aish"
        self.numbers = (1,2,3,4)
    
    def total(self):
        return sum(self._numbers)
    
    def print_10():
        print(10)

```


```python
player1 = LotteryPlayer()
player1.name
```

Class and Static Methods


```python
class LotteryPlayer():
    
    def __init__(self):
        self.name = "Aish"
        self.numbers = (1,2,3,4)
    
    def total(self):
        return sum(self._numbers)
    
    def print_10():
        print(10)
player = LotteryPlayer()
player.print_10()
```


```python
class LotteryPlayer():
    
    def __init__(self):
        self.name = "Aish"
        self.numbers = (1,2,3,4)
    
    def total(self):
        return sum(self._numbers)
    
    @classmethod #when we call the object we do not pass the object but we pass the class
    def print_10(cls):
        print(10,cls)
        
player = LotteryPlayer()
player.print_10()
LotteryPlayer.print_10() 
```


```python
class LotteryPlayer():
    
    def __init__(self):
        self.name = "Aish"
        self.numbers = (1,2,3,4)
    
    def total(self):
        return sum(self._numbers)
    
    @staticmethod #when we call the object we do not pass the object but we pass the class
    def print_10():
        print(10)
        
player = LotteryPlayer()
LotteryPlayer.print_10() 
```


```python
class LotteryPlayer():
    
    def __init__(self):
        self.name = "Aish"
        self.numbers = (1,2,3,4)
    
    def total(self):
        return sum(self.numbers)

class CoolLotteryPlayer(LotteryPlayer):
    pass

player = CoolLotteryPlayer() 
player.total()
```

## Multiple Arguments


```python
def multiple_arguments(*args, **kwargs):
    print(args)
    print(kwargs)
```


```python
multiple_arguments(1,2,3,4,5,6,7,8,9,name='Aish',location='Singapore')
```

## Methodception


```python
def method1(method_next):
    return method_next()

def method2():
    return 2+2

print(method1(method2))
```


```python
print(method1(lambda: 2+3))
```

Lambda + Filter


```python
my_list = [1,2,3,4,5,6,7,8,9]

print(list(filter(lambda x: x%2==0, my_list)))
```


```python
def f(x):
    return x*3
(lambda x: x*3)(5)
```

## Decorators

A decorator is a function that is called before a function


```python
import functools

def my_decorator(func):
    @functools.wraps(func)
    def function_that_runs_func():
        print("I am in the decorator")
        func()
        print("After the decorator")

    return function_that_runs_func
    
```


```python
@my_decorator
def my_function():
    print("I am the function muhahahha")
```


```python
my_function()
```

Decorator with arguments


```python
def decorator_with_arguments(condition):
    def my_decorator(func):
        @functools.wraps(func)
        def function_that_runs_func():
            print("Inside decorator")
            if condition:
                func()
            print("After decorator")
        
        return function_that_runs_func
    return my_decorator
```


```python
@decorator_with_arguments(False)
def my_func():
    print("I am the decorated function")

my_func()
```

## JSON


```python
import json

my_dictionary = {'candidates':{"Barack Obama":
                                 {"state": "Illinois",
                                 "age":"48"},
                               "Joe Biden":
                                   {"state": "Michigan",
                                    "age":"76"},
                               "Donald Trump":
                                   {"state": "New Jersey",
                                    "age":"77"}
                              }
                }
```


```python
my_dictionary['candidates']['Barack Obama']
```




    {'state': 'Illinois', 'age': '48'}




```python
with open('outputs/output.json','w') as out_file:
    json.dump(my_dictionary,out_file)
```


```python
with open('outputs/output.json','r') as in_file:
    input_dict = json.load(in_file)
```


```python
print(input_dict)
print(type(input_dict))
```

    {'candidates': {'Barack Obama': {'state': 'Illinois', 'age': '48'}, 'Joe Biden': {'state': 'Michigan', 'age': '76'}, 'Donald Trump': {'state': 'New Jersey', 'age': '77'}}}
    <class 'dict'>

