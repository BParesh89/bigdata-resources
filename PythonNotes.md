# Python Concepts

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


