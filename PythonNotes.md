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
