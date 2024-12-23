# Lecture 2 Functions

1. Questions
    1. 1.2.6 Could you go over the expression tree for the print statement?
2. Expressions
    1. describes a computation and evaluates
    2. similar to asking your computer a question
    3. Example
        1. 1 + 2 + 3 -5
    4. Call expressions
        1. min, max, etc.
        2. everything can be expressed with call expressions
        3. Anatomy of Call expression
            1. add (2, 3)
                1. add - operator
                2. 2, 3 - operand
        4. Evaluation procedure for call expressions
            1. Evaluate the operator and then the operand subexpressions
            2. Apply the function that is the value of the operator to the arguments that re the values of the operands
        5. Sub expression, expression inside another expression
    5. Names, Assignment, and User-Defined Functions
        1. Using def statement to define own functions
        2. Function allows area to be updated with the new radius value
    6. Types of Expressions
        1. Primitive expressions: 2, add, ‘hello’
        2. Call expressions: max(2,3)
        3. g, h = min, max
            1. g = min
            2. h = max
    7. Environment Diagrams
        1. visualize the interpreter’s process
        2. Code (left): 
            1. Statements and expressions
            2. Arrows indicate evaluation order
        3. Frames (right): 
            1. Each name is bound to a value
            2. Within a frame, a name cannot be repeated
    8. Assignment Statements
        1. Execution rules
            1. Evaluate all expression to the right of = from left to right
            2. Bind all names to the left of = to those resulting values in the current frame
3. Defining Functions
    1. Assignment is a basic means of abstraction: binds names to values
    2. Function definition: binds names to expressions
    3. def statement
    4. Function signature indicates how many arguments a function takes
    5. The function body defines the computation performed when the function is applied
    6. Execution procedure for def statements
        1. Create a function with signature
        2. Set the body of that function indented after the first line
        3. Bind <name> to that function in the current frame
    7. **Don’t necessarily need to memorize all of the procedures, but be familiar with it (included on final exam sheet)**
    8. Return values
        1. returns a value to whoever calls the functions
        2. code that runs after it is not run
    9. Calling User-Defined Functions
        1. Procedure
            1. Add a local frame, forming a new environment
            2. Bind the function’s formal parameters to its arguments in that frame
            3. Execute the body of the function in that new environment
        2. Environment diagram
            1. return value not binding
            2. Name of frame = name of function
        3. Looking up names in Environments
            1. Every expression is evaluated in the context of an environment
        4. An Environment is a sequence of frames
        5. A name evaluates to the value bound to that name in the earliest frame of the current environment in which that name is found
            1. start with current environment, start our way back, until we find it
            2. search local frame first, then global frame
        6. Can only have one copy of a name in a frame
4. Summary
    1. An expression is asking your computer a question
    2.