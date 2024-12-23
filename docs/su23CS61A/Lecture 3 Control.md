# Lecture 3 Control

1. Question
    1. In what case is the parent not global?
    2. What is the difference between a statement and an expression?
2. None Value
    1. Print doesn’t include quotes in string
    
    ```python
    print(print(1), print(2))
    
    '''
    Evaluates to:
    1
    2
    None None
    '''
    ```
    
    1. A function that does not explicitly return a value will return None
        1. None represents nothing in Python
        2. interpreter will not display None as the value of an expression
        3. “print” will display None
3. Pure Functions & Non-Pure Functions
    1. Pure functions
        1. just return values
    2. Non-Pure Functions
        1. have side effects
        2. Print is a non-pure function
            1. Python displays the output “-2”
        3. Nested Expressions with Print
            1. prints 1 and 2 as a side effect
            2. passes in None, into the outside print statement
            3. Print will separate things in commas with a space
4. Multiple Environments
    1. Life cycle of a User-Define Function
        1. Def statement
            1. Name, formal parameter, body, return expression
            2. What happens
                1. A new function is created
                2. name bound to that function in the current frame
        2. Call expression
            1. operator, function, operand
            2. What happens
                1. Operator and operands evaluated
                2. Function called on arguments 
        3. Calling/Applying a Function
            1. A new frame is created
            2. Parameters bound to arguments
            3. Body is executed in that new environment
    2. Multiple Environments in One Diagram
        1. Green arrow: code that was previously evaluated
        2. Red arrow: next line that will be executed
        3. An environment is a sequence of frames
            1. global frame alone
            2. local, then global frame
            3. Every expression is evaluated in the context of an environment
        4. square is defined in the global frame, so its parent is in the global frame
    3. Names have different meanings in Different Environments
        1. A call expression and the body of the function being called are evaluated in different environments
5. Misc Python Features
    1. Can use call expressions as operators
        1. from operator import mul, add, 
    2. Multiple return values
        1. return x, y
        2. quotient, remainder = divide_exact(2023, 10)
        3. Doctest
            1. an example case in the docstring showing how program works
    3. Default arguments
        1. def divide_exact(n, d=10)
            1. you are able to only pass in one argument, d will equal 10
            2. you are able to override by putting in 2 arguments
6. Conditional Statements
    1. Statement
        1. executed by the interpreter to perform an action
    2. Compound statements
        1. The first header determines a statement’s type
        2. header of a clause “controls” the suit that follows
    3. Execution rule
        1. execute the first statement
        2. unless otherwise directed, execute the rest
    4. Execution rule for conditional statements
        1. evaluate the header’s expression
        2. If it is a true value, execute the suite and skip the remaining clauses
    5. Boolean Contexts
        1. False values: False, 0, ‘ ’, None
        2. True values: Anything else (True)
    6. One suite per conditional statement
        1. if, elif, else is all part of one conditional statement
7. Control Expressions
    1. Evaluate the expression “left” **and** “right
        1. evaluate the subexpression left
        2. If it evaluates to a false-y value, then the expression evaluates to <left>
            1. greedy, it was everything to be true
        3. Otherwise, the expression evaluates to <right>
        4. Examples
            1. True and 5 → 5
    2. Evaluate left or right
        1. Evaluate the subexpression <left>
        2. If it evaluates to a truth value, v, the expression evaluates to v
            1. Returns the first falsey value, or the last truthy value
        3. Otherwise, the expression evaluates to <right>
    3. Evaluates not expression
        1. Evaluate the subexpression
        2. If it evaluates to a truth-y value, the expression evaluates to False
        3. Otherwise, the expression evaluates to True
        4. Examples
            1. not True → False
            2. not (None or 0) → True
8. Iteration
    1. While statements
        1. Evaluate the header’s expression
        2. If it is a true value, execute the whole suite, then return to step 1
9. Summary
    1. Pure and non pure functions
        1. print displays a value as a side effect
    2. Multiple environments can exist in a diagram
    3. Fllordiv, truediv, and mod are used in a boolean context
    4. using while statements for iteration