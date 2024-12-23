# Lecture 5 Environments

1. Questions
    1. f2 lambda function being assigned to a parent
2. Environment Diagrams
    1. Environment Diagrams visualize the interpreter’s process
    2. Code on left
        1. statements and expressions
    3. Frames on right
        1. Each name is bound to a value
        2. Names cannot be repeated in a frame
    4. Why use environment diagrams
        1. help us understand why the programs work the way they do
            1. Predict how a program will behave
    5. What we have seen so far
        1. Assignment Statements
        2. Def Statements
        3. Call Expressions
    6. Assignment Statements
        1. Evaluation rules
            1. Evaluate all expressions to the right
            2. Bind all values to the left names
    7. Calling User-Defined Functions
        1. Procedure
            1. Add a local frame
            2. Bind function’s formal parameters to its arguments in that frame
            3. Execute the body of the function in that new environment
        2. **No new frame for built-in functions**
        3. Function’s signature has all the information needed to create a local frame
    8. Frames
        1. keeps track of variable to value bindings
        2. global frame is default starting frame
        3. every call expression has a corresponding frame
        4. **Parent of a function is the frame in which is was defined not called**
            1. important for variable lookup
    9. How to Draw an Environment Diagram
        1. When a function is defined
            1. Create a function value: func <name> (<formal parameters>) [parent=<label>]
            2. Its parent is the current frame, **where function is defined**
        2. When a function is called
            1. Add a local frame
            2. Copy the parent over
            3. Bind the formal parameters to the arguments
            4. Execute the body of the function starting with local frame
        3. Example
            1. You can override a function
    10. Evaluation Order
        1. Evaluate operator, operands, apply operator to operands
3. Lambda Expressions
    1. square = lambda x: x*x
        1. lambda expression evaluates to a function
        2. Must be a single expression (no while loops)
    2. Using line numbers to identify lambda functions
        1. We only know of lambda’s existence at f2, so its parent is f2
4. Environments Enable Higher-Order Functions
    1. Revisiting Evaluation Order
        1. Higher order functions have the same rules
            1. operator, operands, apply operator to operands
5. Currying
    1. Function Currying
        1. Break apart a function that takes in multiple arguments, into nested functions that takes in arguments separately
        2. making a new higher-order function
    2. Can make it easier to think about one argument at a time
6. Summary
    1. Environment diagrams to visualize and understand programming
        1. Diagramming follow the evluation procedure for Python
        2. Think deeply about how the code we write actually works
    2. Lambda expressions
        1. Similar to user-defined functions but anonymous
        2. Simple and can be created for one-time use or stored by assigning as an input to return a function as an output
    3. Currying, to make a HOF