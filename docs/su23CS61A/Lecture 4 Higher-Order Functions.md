# Lecture 4 Higher-Order Functions

1. Questions
    1. When you draw an environment diagram, is the parent function when you call the function or when you define the function?
2. Example: Prime Factorization (Review)
    1. Each positive integer n has a set of primate factors: primes whos product is n
    2. A possible way to solve
        1. Keep dividing by smallest factor until reach 1
    3. Using functions helps keep code readable
3. Example: Iteration (Review)
    1. The Fibonacci Sequence
        1. Multi-line assignment
            1. Calculate each value on the right side
            2. Apply values to left side
4. Control and Call Expressions
    1. Boolean Contexts
        1. What is the boolean value of an expression?
        2. We only care if it is truthy or falsey
        3. Examples: x<0, x==0
    2. If Statements and Call Expressions
        1. Execution rule for Conditional Statements
            1. Evaluate header’s expression
            2. If it is a true value, execute the suite and skip remaining clauses
        2. Trying to recreate if function
            1. if(’header expression’, ‘if suite’, ‘else suite’)
            2. Evaluation Rule for Call Expression
                1. Evaluate operator and operand subexpressions
                    1. Code errors, because program tries to evaluate parameter n//d
5. Higher-Order Functions
    1. Generalizing Over Computational Processes
        1. Common structure among functions may be a computational process, rather than a number
        2. Generalizable Function
            1. Can have a general function that does summation
            2. Use a term function to do an operation on k
6. Types of Higher-Order Functions
    1. Environments Enable Higher-Order Functions
        1. Higher-order functions
            1. A function that takes a function as an argument value
            2. A function that returns a function as a return value
        2. first class
            1. Functions are values in our programming language
    2. Names can be bound to Functional Arguments
        1. Applying a user-defined function
            1. Create new frame
            2. bind formal parameters to arguments
            3. Execute the body
7. Functions as Return Values
    1. Can return a function to generalize
    2. Locally Defined Functions
        1. Functions defined within other function bodies are bound to names in a local frame
        2. Can refer to names in the enclosing function
    3. Environment Diagrams for Nested Def Statements
        1. Look at parent function before global
        2. Every user-defined function has a parent frame (often global)
        3. Parent of a frame is the parent of the function called
    4. Call Expressions as Operator Expressions
        1. make_adder(1)(2)
            1. make_adder(1) is actually the operator
                1. expression evaluates to a function
            2. (2) is the operand
8. How to Draw an Environment Diagram
    1. When a function is defined
        1. Its parent is the current frame
        2. Bind name to the function value in the current frame
    2. When a function is called
        1. Add a local frame, titled with the <name> of the function being called
        2. **Copy the parent of the function to the local frame**
            1. based on the function definition
        3. Bind the formal parameters to the arguments in the local frame
        4. Execute the body of the function in the environment that starts with the local frame
9. Local Names
    1. Local Names are not Visible to Other (Non-Nested) Functions
        1. function g is defined in global frame
            1. cannot access function f’s frame
10. Function Composition
11. Lambda Expressions
    1. Another way to make a function
    
    ```python
    lambda x: x**2
    
    square = lambda x: x**2
    ```
    
    1. square = x*x (expression that evaluates to a number)
    2. square = lambda x: x*x (also an expression: evaluates to a function)
        1. def vs lambda statement
            1. def statement doesn’t return anything
            2. lambda returns a function value
    3. Syntax
        1. lambda - Function
        2. x - with formal parameter x
        3. x*x - returns the value of “x*x”
    4. Lambda expressions cannot contain statements at all
    5. Useful for inputs into other functions
        1. faster way than def to make functions
12. Lambda Expressions vs def statements
    1. Both create a function with same domain, range, behavior
    2. Both bind function tothe name square
    3. Only the def statement gives the function an intrinsic name
        1. shows up in environment diagrams, but doesn’t affect execution
        2. Put line number for lambda, as there can be different lambda functions
        3. Def functions don’t need line number because there can only be one name of that
13. Higher Order functions with Lambdas
    1. Lambdas can return another lambda
14. Summary
    1. Functional abstraction
        1. use logic before
    2. Well defined functions can help redundancy in our code
    3. high-order functions → input/output functions
    4. Functions can be nested within other functions
    5. Control structures have different evaluation than functions
    6. Lambda expressions are a quick way to define simple functions within a single line