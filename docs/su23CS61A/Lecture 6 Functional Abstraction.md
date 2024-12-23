# Lecture 6 Functional Abstraction

1. Questions
    1. slide 8, intrinsic name square question
    2. how to know what is a runtime error vs syntax error
2. Decorators
    
    ```python
    @trace
    def square(x):
    	return x*x
    
    """
    Defining trace ourself
    """
    def trace1(fn):
    	fn = <function with 1 arg>
    	def traced(x):
    		print("Calling", fn, "on argument", x)
    		return fn(x)
    	return traced
    ```
    
    1. Writing @trace
        1. Breaking down every function call
        2. Telling us the input and output
        3. Each time we call a function, tells us what we are calling the function on
        4. Way to transform a function into another function
        5. Decorator has to take in a function and return a function
            1. Overrides the current function
            2. printing value first, then applying the function
3. Return
    1. Return Statements
        1. completes the evaluation of a call expression and provides it value
        2. switch back to previous environment, f(x) now has a value
        3. Only one return statement is ever executed while executing body of function
    2. Abstraction
        1. Square has the intrinsic name sqare (not needed)
        2. Names don’t matter for correctness, but matter a lot for composition
            1. best documented in docstring
            2. Function names typically convey their affect, behavior, value returned
    3. Which Values Deserve a Name
        1. reasons to add a new name
            1. repeated compound expression
            2. Meaningful parts of complex expressions
4. Errors and Tracebacks
    1. Syntax Errors
        1. Detected by the Python interpreter before program executes
        2. Rules about form, parentheses
    2. Runtime Errors
        1. Detected while running
    3. Logic and Behavior Errors
        1. Not detected by Python interpreter
        2. Program doesn’t crash, but gives wrong output
        3. This is why we use tests
    4. Common Bugs from Students
        1. NameError
            1. spelling
        2. SyntaxError
            1. Missing parenthesis
        3. Logic and Behavior Errors
            1. = vs ==
            2. Off by 1 errors
        4. IndentationError
        5. Type Error
            1. invalid types for an operator
            2. using non-function objects in a function call
            3. passing incorrect number of arguments to a function
        6. IndexError
            1. Index sequence with a # that exceeds size of sequence
5. Debugging
    1. To run the doctest above
    2. python3 -m doctest <filename>.py
        1. nothing is displayed when doctest passed
    3. You should test edge cases
    4. When running debug
        1. put a variable debug and you can toggle prints when debugging
    5. assert
        1. assert isinstance(x, int), “the input of x has to be an int”
    6. Use print(’DEBUG:’) for okpy
6. Implementing Functions
    1. Write about what you know about the problem
    2. Read the description
    3. Look at the examples
    4. Read the template
        1. you may be able to change your own solution into the template
        2.