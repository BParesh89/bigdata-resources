## Python Concepts

### Python Keywords

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
    
### Python Identifiers

An identifier is a name given to entities like class, functions, variables, etc. It helps to differentiate one entity from another.

#### Rules for writing identifiers

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

### I/O formatting

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
    
### Operators in python

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
    

# Logical operators

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
