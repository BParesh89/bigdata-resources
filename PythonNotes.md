# Python Concepts

__References -->__ [Programiz](https://www.programiz.com/python-programming)

## Python Keywords

Keywords are the reserved words in Python.

We cannot use a keyword as a variable name, function name or any other identifier. They are used to define the syntax and structure of the Python language.

In Python, keywords are case sensitive.

All the keywords except `True`, `False` and `None` are in lowercase and they must be written as they are. The list of all the keywords is given below.

    False	await	else	import	pass
    None	break	except	in	raise
    True	class	finally	is	return
    and	continue	for	lambda	try
    as	def	from	nonlocal	while
    assert	del	global	not	with
    async	elif	if	or	yield
    
## Python Identifiers

An identifier is a name given to entities like class, functions, variables, etc. It helps to differentiate one entity from another.

### Rules for writing identifiers

1. Identifiers can be a combination of letters in lowercase (a to z) or uppercase (A to Z) or digits (0 to 9) or an underscore _. Names like myClass, var_1 and print_this_to_screen, all are valid example.

2. An identifier cannot start with a digit. 1variable is invalid, but variable1 is a valid name.

3. Keywords cannot be used as identifiers.

   `global = 1`

Output

    File "<interactive input>", line 1
      global = 1
             ^
    SyntaxError: invalid syntax

4. We cannot use special symbols like !, @, #, $, % etc. in our identifier.

   `a@ = 0`

### Things to Remember
Python is a case-sensitive language. This means, `Variable` and `variable` are not the same.

Always give the identifiers a name that makes sense. While `c = 10` is a valid name, writing `count = 10` would make more sense, and it would be easier to figure out what it represents when you look at your code after a long gap.

Multiple words can be separated using an underscore, like `this_is_a_long_variable`.

__Multiline statements can be put in python using below syntaxes :__

    a = 1 + 2 + 3 + \
        4 + 5 + 6 + \
        7 + 8 + 9
        
__Insides parenthesis like `()`, `[]`, `{}`, line continuation is implied.__

    a = (1 + 2 + 3 +
        4 + 5 + 6 +
        7 + 8 + 9)
        
We can also put multiple statements in a single line using semicolons, as follows:

`a = 1; b = 2; c = 3`

## I/O formatting

We can use `print()`  for printing to console in python like below:

    print(1, 2, 3, 4)
    print(1, 2, 3, 4, sep='*')
    print(1, 2, 3, 4, sep='#', end='&')
        
Output will be

    1 2 3 4
    1*2*3*4
    1#2#3#4&
    
We can format the `print()` output like below ;

    >>> x = 5; y = 10
    >>> print('The value of x is {} and y is {}'.format(x,y))
    The value of x is 5 and y is 10
    
We can also give numbered arguments in `print()` like below :

    print('I love {0} and {1}'.format('bread','butter'))
    print('I love {1} and {0}'.format('bread','butter'))
    
We can also format decimal point numbers like below :

    >>> x = 12.3456789
    >>> print('The value of x is %3.2f' %x)
    The value of x is 12.35
    >>> print('The value of x is %3.4f' %x)
    The value of x is 12.3457

We can take input from user via console in python using `input()` function :

    >>> num = input('Enter a number: ')
    Enter a number: 10
    >>> num
    '10'
    
## Operators in python

Operators are special symbols in Python that carry out arithmetic or logical computation. The value that the operator operates on is called the operand.

For example:

    >>> 2+3
    5
    
### Arithmetic operators

Arithmetic operators are used to perform mathematical operations like addition, subtraction, multiplication, etc.

| Operator | Meaning | Example |
| --- | --- | --- |
| + | Add two operands or unary plus |	x + y+ 2 |
| - | Subtract right operand from the left or unary minus |	x - y- 2 |
| * | Multiply two operands | x * y |
| / | Divide left operand by the right one (always results into float) | x / y |
| % | Modulus - remainder of the division of left operand by the right | x % y (remainder of x/y) |
| // | Floor division - division that results into whole number adjusted to the left in the number line | x // y |
| ** | Exponent - left operand raised to the power of right | x**y (x to the power y) |

Example 1: Arithmetic operators in Python

    x = 15
    y = 4

    # Output: x + y = 19
    print('x + y =',x+y)

    # Output: x - y = 11
    print('x - y =',x-y)

    # Output: x * y = 60
    print('x * y =',x*y)

    # Output: x / y = 3.75
    print('x / y =',x/y)

    # Output: x // y = 3
    print('x // y =',x//y)

    # Output: x ** y = 50625
    print('x ** y =',x**y)


### Comparison operators

Comparison operators are used to compare values. It returns either True or False according to the condition.

| Operator | Meaning | Example |
| --- | --- | --- |
| > | Greater than - True if left operand is greater than the right | x > y |
| < | less than - True if left operand is less than the right |	x < y |
| == | Equal to - True if both operands are equal |	x == y |
| != | Not equal to - True if operands are not equal | x != y |
| >= | Greater than or equal to - True if left operand is greater than or equal to the right | x >= y |
| <= |Less than or equal to - True if left operand is less than or equal to the right |	x <= y |


Example 2: Comparison operators in Python

    x = 10
    y = 12

    # Output: x > y is False
    print('x > y is',x>y)

    # Output: x < y is True
    print('x < y is',x<y)

    # Output: x == y is False
    print('x == y is',x==y)

    # Output: x != y is True
    print('x != y is',x!=y)

    # Output: x >= y is False
    print('x >= y is',x>=y)

    # Output: x <= y is True
    print('x <= y is',x<=y)
    

### Logical operators

Logical operators are the and, or, not operators.

| Operator | Meaning | Example |
| --- | --- | --- |
| and |	True if both the operands are true | x and y |
| or | True if either of the operands is true |	x or y |
| not | True if operand is false (complements the operand) | not x |

Example 3: Logical Operators in Python

    x = True
    y = False

    print('x and y is',x and y)

    print('x or y is',x or y)

    print('not x is',not x)
    
Output

    x and y is False
    x or y is True
    not x is False
    
### Bitwise operators

Bitwise operators act on operands as if they were strings of binary digits. They operate bit by bit, hence the name.

For example, 2 is 10 in binary and 7 is 111.

In the table below: Let `x = 10` (0000 1010 in binary) and `y = 4` (0000 0100 in binary)


| Operator | Meaning | Example |
| --- | --- | --- |
| & | Bitwise AND |	x & y = 0 (0000 0000) |
| &#124; | Bitwise OR | x &#124; y = 14 (0000 1110) |
| ~ | Bitwise NOT |	~x = -11 (1111 0101) |
| ^ | Bitwise XOR |	x ^ y = 14 (0000 1110) |
| >> | Bitwise right shift | x >> 2 = 2 (0000 0010) |
| << | Bitwise left shift |	x << 2 = 40 (0010 1000) |

### Assignment operators

Assignment operators are used in Python to assign values to variables.

`a = 5` is a simple assignment operator that assigns the value 5 on the right to the variable a on the left.

There are various compound operators in Python like `a += 5` that adds to the variable and later assigns the same. It is equivalent to `a = a + 5`.

| Operator | Example | Equivalent to |
| --- | --- | --- |
| = | x = 5 | x = 5 |
| += | x += 5 |	x = x + 5 | 
| -= | x -= 5 |	x = x - 5 |
| *= |	x *= 5 | x = x * 5 |
| /= |	x /= 5 | x = x / 5 |
| %= | x %= 5 |	x = x % 5 |
| //= |	x //= 5 | x = x // 5 |
| **= |	x **= 5 | x = x ** 5 |
| &= | x &= 5 |	x = x & 5 |
|  &#124;= | x  &#124;= 5 |	x = x  &#124; 5 |
| ^= | x ^= 5 | x = x ^ 5 |
| >>= | x >>= 5 | x = x >> 5 |
| <<= | x <<= 5 | x = x << 5 |

### Special operators

Python language offers some special types of operators like the identity operator or the membership operator. They are described below with examples.

#### Identity operators
`is` and `is not` are the identity operators in Python. They are used to check if two values (or variables) are located on the same part of the memory. Two variables that are equal does not imply that they are identical.

| Operator | Meaning | Example |
| --- | --- | --- |
| is | True if the operands are identical (refer to the same object) |	x is True |
| is not | True if the operands are not identical (do not refer to the same object) | x is not True |

Example 4: Identity operators in Python

    x1 = 5
    y1 = 5
    x2 = 'Hello'
    y2 = 'Hello'
    x3 = [1,2,3]
    y3 = [1,2,3]

    # Output: False
    print(x1 is not y1)

    # Output: True
    print(x2 is y2)

    # Output: False
    print(x3 is y3)


Output

    False
    True
    False

#### Membership operators

`in` and `not in` are the membership operators in Python. They are used to test whether a value or variable is found in a sequence (string, list, tuple, set and dictionary).

In a dictionary we can only test for presence of key, not the value.

| Operator | Meaning | Example |
| --- | --- | --- |
| in | True if value/variable is found in the sequence | 5 in x |
| not in | True if value/variable is not found in the sequence | 5 not in x |

Example #5: Membership operators in Python

    x = 'Hello world'
    y = {1:'a',2:'b'}

    # Output: True
    print('H' in x)

    # Output: True
    print('hello' not in x)

    # Output: True
    print(1 in y)

    # Output: False
    print('a' in y)


## Python Namespaces

A namespace in Python ensures that object names in a program are unique and can be used without any conflict. Python implements these namespaces as dictionaries with 'name as key' mapped to a corresponding 'object as value'. This allows for multiple namespaces to use the same name and map it to a separate object. A few examples of namespaces are as follows:

* __Local Namespace__ includes local names inside a function. the namespace is temporarily created for a function call and gets cleared when the function returns.
* __Global Namespace__ includes names from various imported packages/ modules that is being used in the current project. This namespace is created when the package is imported in the script and lasts until the execution of the script.
* __Built-in Namespace__ includes built-in functions of core Python and built-in names for various types of exceptions.

Lifecycle of a namespace depends upon the scope of objects they are mapped to. If the scope of an object ends, the lifecycle of that namespace comes to an end. Hence, it isn't possible to access inner namespace objects from an outer namespace.

### Scope Resolution

ToDo.

## Python Flow Control

### If else

Example 1:

    num = 3
    if num >= 0:
        print("Positive or Zero")
    else:
        print("Negative number")

Example 2:

    num = 3.4
    if num > 0:
        print("Positive number")
    elif num == 0:
        print("Zero")
    else:
        print("Negative number")


### For loop

To iterate over a collection like list , we can use for-loop like below:

    # List of numbers
    numbers = [6, 5, 3, 8, 4, 2, 5, 4, 11]

    # variable to store the sum
    sum = 0

    # iterate over the list
    for val in numbers:
        sum = sum+val

    print("The sum is", sum)

To use between a range of number, we can use `range()` function like below :

    for i in range(1,10):
        print(i)

A for loop can have an optional else block as well. The else part is executed if the items in the sequence used in for loop exhausts.

Here is an example to illustrate this.

digits = [0, 1, 5]

    for i in digits:
        print(i)
    else:
        print("No items left.")

Output of it is 

    0
    1
    5
    No items left.

### while loop

Example 1

    n = 10
    # initialize sum and counter
    sum = 0
    i = 1
    while i <= n:
        sum = sum + i
        i = i+1    # update counter

    # print the sum
    print("The sum is", sum)

We can also use `while loop` with `else` like below :

    counter = 0
    while counter < 3:
        print("Inside loop")
        counter = counter + 1
    else:
        print("Inside else")

### break statement

The `break` statement terminates the loop containing it. Control of the program flows to the statement immediately after the body of the loop.

If the `break` statement is inside a nested loop (loop inside another loop), the break statement will terminate the innermost loop.

Example 1:

    for val in "string":
        if val == "i":
            break
        print(val)

    print("The end")

Output is 

    s
    t
    r
    The end

### continue statement

The `continue` statement is used to skip the rest of the code inside a loop for the current iteration only. Loop does not terminate but continues on with the next iteration.

Example :

    for val in "string":
        if val == "i":
            continue
        print(val)

    print("The end")

Output is :

    s
    t
    r
    n
    g
    The end

### pass statement

In Python programming, the `pass` statement is a null statement. The difference between a comment and a `pass` statement in Python is that while the interpreter ignores a comment entirely, `pass` is not ignored.

However, nothing happens when the `pass` is executed. It results in no operation (NOP).

Example :

    '''pass is just a placeholder for
    functionality to be added later.'''
    sequence = {'p', 'a', 's', 's'}
    for val in sequence:
        pass

## Functions

In Python, a function is a group of related statements that performs a specific task.

Functions help break our program into smaller and modular chunks. As our program grows larger and larger, functions make it more organized and manageable.

Furthermore, it avoids repetition and makes the code reusable.

Example 

    def greet(name):
        """
        This function greets to
        the person passed in as
        a parameter
        """
        print("Hello, " + name + ". Good morning!")

To call a function, we can call it like below :

    >>> greet('Paul')
    Hello, Paul. Good morning!

Function can return value as well using `return` statement like below :

    >>> def addition(x,y):
    ...     return x+y;
    >>> addition(2,3) 
    5

### Types of Functions
Basically, we can divide functions into the following two types:

1. [Built-in functions](https://www.programiz.com/python-programming/methods/built-in) - Functions that are built into Python.

2. __User-defined functions__ - Functions defined by the users themselves. Example is  `addition` function defined above.

### Arguments in function

Functions can accept arguments as well as saw in function `addition` above.

It can have default arguments as well like :

    def greet(name, msg="Good morning!"):
        """
        This function greets to
        the person with the
        provided message.

        If the message is not provided,
        it defaults to "Good
        morning!"
        """

        print("Hello", name + ', ' + msg)


    greet("Kate")
    greet("Bruce", "How do you do?")

Output is 

    Hello Kate, Good morning!
    Hello Bruce, How do you do?

__All arguments which are not having default value defined in function definition must be on left side of argument having default value.

This means to say, non-default arguments cannot follow default arguments. For example, if we had defined the function header above as:

`def greet(msg = "Good morning!", name):`

We would get an error as:

`SyntaxError: non-default argument follows default argument`

Python also allows us to pass arbitrary number of arguments to function using *args. 

In the function definition, we use an asterisk (*) before the parameter name to denote this kind of argument. Here is an example.

    def greet(*names):
        """This function greets all
        the person in the names tuple."""

        # names is a tuple with arguments
        for name in names:
            print("Hello", name)


    greet("Monica", "Luke", "Steve", "John")

Output

    Hello Monica
    Hello Luke
    Hello Steve
    Hello John

### Recursive functions

Recursive functions are functions which are calling themselves.

Example :

    def factorial(x):
        """This is a recursive function
        to find the factorial of an integer"""

        if x == 1:
            return 1
        else:
            return (x * factorial(x-1))


    num = 3
    print("The factorial of", num, "is", factorial(num))

Output

`The factorial of 3 is 6`

__By default, the maximum depth of recursion in Python is 1000. If the limit is crossed, it results in `RecursionError`.__

### Anonymous/Lambda function in Python

In Python, an anonymous function is a function that is defined without a name.

While normal functions are defined using the `def` keyword in Python, anonymous functions are defined using the `lambda` keyword.

Example :

    # Program to show the use of lambda functions
    double = lambda x: x * 2

    print(double(5))

`lambda` functions can be used with `map` and `filter` function as well like below:

    >>> my_list = [1, 5, 4, 6, 8, 11, 3, 12]
    >>> new_list = list(filter(lambda x: (x%2 == 0) , my_list))
    >>> print(new_list)
    [4, 6, 8, 12]
    >>> new_list1 = list(map(lambda x: x * 2 , my_list))
    >>> print(new_list1)
    [2, 10, 8, 12, 16, 22, 6, 24]


## Python Data Structures

### List

In Python programming, a list is created by placing all the items (elements) inside square brackets [], separated by commas.

It can have any number of items and they may be of different types (integer, float, string etc.).

    # empty list
    my_list = []

    # list of integers
    my_list = [1, 2, 3]

    # list with mixed data types
    my_list = [1, "Hello", 3.4]

List is mutable.

Methods are append(value), insert(pos,value),pop(index)

List comprehension is an elegant and concise way to create a new list from an existing list in Python.

A list comprehension consists of an expression followed by for statement inside square brackets.

Here is an example to make a list with each item being increasing power of 2.

    pow2 = [2 ** x for x in range(10)]
    print(pow2)
    # output - [1, 2, 4, 8, 16, 32, 64, 128, 256, 512]

### Tuple

Tuple is similar to list but immutable. 

A tuple is created by placing all the items (elements) inside parentheses (), separated by commas. The parentheses are optional, however, it is a good practice to use them.

A tuple can have any number of items and they may be of different types.

Example :

    # Different types of tuples

    # Empty tuple
    my_tuple = ()
    print(my_tuple)

    # Tuple having integers
    my_tuple = (1, 2, 3)
    print(my_tuple)

    # tuple with mixed datatypes
    my_tuple = (1, "Hello", 3.4)
    print(my_tuple)

    # nested tuple
    my_tuple = ("mouse", [8, 4, 6], (1, 2, 3))
    print(my_tuple)

We can pack and unpack tuple like below ;

    my_tuple = 3, 4.6, "dog"
    print(my_tuple)

    # tuple unpacking is also possible
    a, b, c = my_tuple

Indexing and slicing is similar to list.

Elements of a tuple cannot be changed once they have been assigned. But, if the element is itself a mutable data type like list, its nested items can be changed.

We can also assign a tuple to different values (reassignment).

    # Changing tuple values
    my_tuple = (4, 2, 3, [6, 5])


    # TypeError: 'tuple' object does not support item assignment
    # my_tuple[1] = 9

    # However, item of mutable element can be changed
    my_tuple[3][0] = 9    # Output: (4, 2, 3, [9, 5])
    print(my_tuple)

    # Tuples can be reassigned
    my_tuple = ('p', 'r', 'o', 'g', 'r', 'a', 'm', 'i', 'z')

    # Output: ('p', 'r', 'o', 'g', 'r', 'a', 'm', 'i', 'z')
    print(my_tuple)

### Set

A set is an unordered collection of items. Every set element is unique (no duplicates) and must be immutable (cannot be changed).

However, a set itself is mutable. We can add or remove items from it.

Sets can also be used to perform mathematical set operations like union, intersection, symmetric difference, etc.

Example :

    # Different types of sets in Python
    # set of integers
    my_set = {1, 2, 3}
    print(my_set)

    # set of mixed datatypes
    my_set = {1.0, "Hello", (1, 2, 3)}
    print(my_set)

Add() method can be used to insert single element and update() method can be used to insert multiple elements using a list or tuple.

    # add an element
    # Output: {1, 2, 3}
    my_set.add(2)
    print(my_set)

    # add multiple elements
    # Output: {1, 2, 3, 4}
    my_set.update([2, 3, 4])
    print(my_set)

A particular item can be removed from a set using the methods `discard()` and `remove()`.

The only difference between the two is that the `discard()` function leaves a set unchanged if the element is not present in the set. On the other hand, the `remove()` function will raise an error in such a condition (if element is not present in the set).

Similarly, we can remove and return an item using the `pop()` method.

__Since set is an unordered data type, there is no way of determining which item will be popped. It is completely arbitrary.__

We can also remove all the items from a set using the `clear()` method.

#### Set operations

To Do.

### Dictionary

Python dictionary is an unordered collection of items. Each item of a dictionary has a key/value pair.

Dictionaries are optimized to retrieve values when the key is known.

While the values can be of any data type and can repeat, keys must be of immutable type (string, number or tuple with immutable elements) and must be unique.

    # empty dictionary
    my_dict = {}

    # dictionary with integer keys
    my_dict = {1: 'apple', 2: 'ball'}

    # dictionary with mixed keys
    my_dict = {'name': 'John', 1: [2, 4, 3]}

    # using dict()
    my_dict = dict({1:'apple', 2:'ball'})

    # from sequence having each item as a pair
    my_dict = dict([(1,'apple'), (2,'ball')])

We can also create dicitionary using `dict()` method. 

To access element of any dictionary we can use like :

    # Output: Jack
    print(my_dict['name'])

We can remove a particular item in a dictionary by using the pop() method. This method removes an item with the provided key and returns the value.

The popitem() method can be used to remove and return an arbitrary (key, value) item pair from the dictionary. All the items can be removed at once, using the clear() method.

We can also use the del keyword to remove individual items or the entire dictionary itself.

    # Removing elements from a dictionary

    # create a dictionary
    squares = {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}

    # remove a particular item, returns its value
    # Output: 16
    print(squares.pop(4))

    # Output: {1: 1, 2: 4, 3: 9, 5: 25}
    print(squares)

    # remove an arbitrary item, return (key,value)
    # Output: (5, 25)
    print(squares.popitem())

    # Output: {1: 1, 2: 4, 3: 9}
    print(squares)

    # remove all items
    squares.clear()

    # Output: {}
    print(squares)

    # delete the dictionary itself
    del squares

    # Throws Error
    print(squares)

`keys()` and `values()` methods will give new object of keys and values in dictionary respectively.

## Python File and Exception Handling
Example :

    try:
    f = open("test.txt", encoding = 'utf-8')
    # perform file operations
    finally:
    f.close()

The best way to close a file is by using the with statement. This ensures that the file is closed when the block inside the with statement is exited.

We don't need to explicitly call the close() method. It is done internally.

    with open("test.txt", encoding = 'utf-8') as f:
    # perform file operations


To Do.

## OOPS in Python

### Classes and Objects in Python
An object is simply a collection of data (variables) and methods (functions) that act on those data. Similarly, a class is a blueprint for that object.

We can think of class as a sketch (prototype) of a house. It contains all the details about the floors, doors, windows etc. Based on these descriptions we build the house. House is the object.

A class is a blueprint of objects.

An object (instance) is an instantiation of a class. When class is defined, only the description for the object is defined. Therefore, no memory or storage is allocated.

Example 1: Creating Class and Object in Python

    class Parrot:

        # class attribute
        species = "bird"

        # instance attribute
        def __init__(self, name, age):
            self.name = name
            self.age = age

    # instantiate the Parrot class
    blu = Parrot("Blu", 10)
    woo = Parrot("Woo", 15)

    # access the class attributes
    print("Blu is a {}".format(blu.__class__.species))
    print("Woo is also a {}".format(woo.__class__.species))

    # access the instance attributes
    print("{} is {} years old".format( blu.name, blu.age))
    print("{} is {} years old".format( woo.name, woo.age))

Output

    Blu is a bird
    Woo is also a bird
    Blu is 10 years old
    Woo is 15 years old

`__init__` is the initializer method(constructor) that is first run as soon as the object is created.

`self` is used to represent the instance of class. With this keyword, you can access the attributes and method of a class in python. It binds the attributes with given arguemnt.

### Encapsulation

Using OOP in python ,we can restrict access to methods and variables. This prevents data from direct modification which is called encapsulation. In Python, we can have `private` and `protected` variable.

Protected variables are accessible only by the class derived from its class. They are declared with appending `_`(single underscore) before the name of a variable in class.

Private variables are only accessible in the class in which they are declared. They are declated with appending `__` before(double underscore) the name of variable in class.

Reference --> [https://www.geeksforgeeks.org/access-modifiers-in-python-public-private-and-protected/](https://www.geeksforgeeks.org/access-modifiers-in-python-public-private-and-protected/)

### Inheritance in Python

Inheritanace refers to defining a new class using little or no modification to an existing class. The new class is called __dervied(or child) class__ and existing class is called __base(or parent) class__. 

Example 

    # Base class
    class Polygon:
        def __init__(self, no_of_sides):
            self.n = no_of_sides
            self.sides = [0 for i in range(no_of_sides)]

        def inputSides(self):
            self.sides = [float(input("Enter side "+str(i+1)+" : ")) for i in range(self.n)]

        def dispSides(self):
            for i in range(self.n):
                print("Side",i+1,"is",self.sides[i])

    # Derived class
    class Triangle(Polygon):
        def __init__(self):
            Polygon.__init__(self,3)  # or super.__init__(self,3)

        def findArea(self):
            a, b, c = self.sides
            # calculate the semi-perimeter
            s = (a + b + c) / 2
            area = (s*(s-a)*(s-b)*(s-c)) ** 0.5
            print('The area of the triangle is %0.2f' %area)

Output

    >>> t = Triangle()

    >>> t.inputSides()
    Enter side 1 : 3
    Enter side 2 : 5
    Enter side 3 : 4

    >>> t.dispSides()
    Side 1 is 3.0
    Side 2 is 5.0
    Side 3 is 4.0

    >>> t.findArea()
    The area of the triangle is 6.00

Above, `super` keyword can be used to refer the base class.

Two built-in functions `isinstance()` and `issubclass()` are used to check inheritances.

__Python also supports mutliple inheritance.__ A derived class can inherit more than one class.

Example :

    class Base1:
        pass

    class Base2:
        pass

    class MultiDerived(Base1, Base2):
        pass

__Python supports multi-level inheritance as well.__ A class can also inherit from a derived class.It can be of any depth in Python.

In multilevel inheritance, features of the base class and the derived class are inherited into the new derived class.

Example

    class Base:
        pass

    class Derived1(Base):
        pass

    class Derived2(Derived1):
        pass

Multiple and multi-level inheritance creates a problem for searching the attributes in which class first. 

In the multiple inheritance scenario, any specified attribute is searched first in the current class. After it , the search continues in parent class in depth first, left right fashion without searching the same class twice. These set of rules to find the order where to look for method is called __Method Resolution Order(MRO).__ MRO of an class can be looked with `__mro__` attribute or `mro()` method.

Example

    >>> MultiDerived.__mro__
    (<class '__main__.MultiDerived'>,
    <class '__main__.Base1'>,
    <class '__main__.Base2'>,
    <class 'object'>)

## Iterators

Iterators are the objects that can be iterated upon. Examples are list, set, tuple etc.
These objects will simply return data, one element at a time.

Technically, a python iterator object must implement two methods : `__iter__()` and `__next__()`, collectively called the iterator protocol.    

To get iterator from python list, tuple etc, we need to use `iter()` function on them. To get element from them, we need to call `next()` like below :

    >>> myiter = iter([1,2,3])
    >>> next(myiter)
    1   
    >>> next(myiter)
    2
    >>> next(myiter)
    3
    >>> next(myiter)
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    StopIteration

After elements are finished, if we call iter(), it gives error `StopIteration`.


## Generators

Generators are fairly simple way of creating iterators. We dont need to implement whole class with `__iter__()` and `__next()__` methods. 

A generator is a function that returns an object(iterator) which we can iterate over(one value at a time).

Generator can be defined as similar to normal function, only difference is , it uses `yield` keyword instead of `return`.  

The differnce is that while a `return` statement terminates a function entirely, `yield` statement pauses the function saving all its state and later continues from there on successive calls.

Example 

    ## generate fibonacci numbers upto n
    def fib(n):
        p, q = 0, 1
        while(p < n):
            yield p
            p, q = q, p + q

    x = fib(10)    # create generator object 
    
    ## iterating using __next__(), for Python2, use next()
    x.__next__()    # output => 0
    x.__next__()    # output => 1
    x.__next__()    # output => 1
    x.__next__()    # output => 2
    x.__next__()    # output => 3
    x.__next__()    # output => 5
    x.__next__()    # output => 8
    x.__next__()    # error
    
    ## iterating using loop
    for i in fib(10):
        print(i)    # output => 0 1 1 2 3 5 8

Similar to list comprehension, we can have __generator comprehension__ as well. It is very similar to list comprehension, but major difference is list comprehension produces entire list after execution while generator doesn't return any list or value, it returns a generator object. We need to call next to get value out of it. This way it supports `lazy evaluation` in scala.

    >>> my_list = [1,2,3]
    >>> gener = (x*x for x in my_list)
    >>> print(gener)
    <generator object <genexpr> at 0x000001CC3FF4DF90>
    >>> next(gener)
    1
    >>> next(gener)
    4
    >>> next(gener)
    9
    >>> next(gener)
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    StopIteration

## Closures in Python

A closure is a function object that remembers values in enclosing scope even if they are not present in memory.

Example :

    def print_msg(msg):
        # This is the outer enclosing function

        def printer():
            # This is the nested function
            print(msg)

        return printer  # returns the nested function


    # Now let's try calling this function.
    # Output: Hello
    another = print_msg("Hello")
    another()

Output

`Hello`

The `print_msg()` function was called with the string "Hello" and the returned function was bound to the name another. On calling `another()`, the message was still remembered although we had already finished executing the `print_msg()` function.

This technique by which some data ("Hello in this case) gets attached to the code is called __closure__ in Python.

This value in the enclosing scope is remembered even when the variable goes out of scope or the function itself is removed from the current namespace.

The criteria that must be met to create closure in Python are summarized in the following points.

* We must have a nested function (function inside a function).

* The nested function must refer to a value defined in the enclosing function.

*The enclosing function must return the nested function.

__When and Why to use Closures__

* As closures are used as callback functions, they provide some sort of data hiding. This helps us to reduce the use of global variables.

* When we have few functions in our code, closures prove to be efficient way. But if we need to have many functions, then go for class (OOP).

## Decorators

Decorators in python are essentially functions that add additional functionality to an existing function without changing its structure. 

They are represented by the @decorator_name in Python and are called in bottom-up fashion. For example:

    # decorator function to convert to lowercase
    def lowercase_decorator(function):
        def wrapper():
            func = function()
            string_lowercase = func.lower()
            return string_lowercase
        return wrapper

    # decorator function to split words
    def splitter_decorator(function):
        def wrapper():
            func = function()
            string_split = func.split()
            return string_split
        return wrapper

    @splitter_decorator	# this is executed next
    @lowercase_decorator	# this is executed first
    def hello():
        return 'Hello World'

    hello() 	 # output => [ 'hello' , 'world' ]

The beauty of the decorators lies in the fact that besides adding functionality to the output of the method, they can even accept arguments for functions and can further modify those arguments before passing them.


