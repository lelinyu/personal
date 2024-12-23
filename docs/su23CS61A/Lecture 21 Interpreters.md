# Lecture 21 Interpreters

1. Questions
2. Programming Languages
    1. High level → Assembly → Machine
    2. Machine languages
        1. statements interpreted by the hardware itself
    3. High-level languages
        1. statements and expressions are interpreted by another program or compiled into another language
3. Compilers
    1. translate source code into machine code so that the machine code can be distributed and run repeatedly
    2. Interpreters
        1. run source code directly without first compiling it into machine code
    3. Understanding source code
        1. parser must be written to understand that source code
4. Parsing
    1. Reading Scheme Lists
        1. All call expressions in Scheme are represented by a Scheme list
        2. Scheme list is written as elements in parentheses
        3. Each element can be a combination or primitive
    2. Parser takes in text and returns an expression that represents the text in a tree-like structure
    3. Lexical Analysis
        1. converts input text into a list of tokens
        2. each token represents the smallest unit of information
    4. Syntatic Analysis
        1. identifies the hierachical structure of an expression
        2. symbols can be nested
    5. Pair Abstraction
        1. A pair is similar to a linked list
    6. Generating Pairs
        1. we define a function called scheme_read that will consume the input tokens for exactly one expression
5. The Calculator Language
    1. Just primitive expressions and call expressions
    2. Call expression is a combination that begins with operator followed by 0 or more expressions
    3. Expression Trees
        1. When we want to use control, we follow the same evaluation procedure
6. Evaluation
    1. Computes the value of an expression, which is always a number
    2. In calculator, an expression is either a number or a Pair
    3. Language semantics
        1. A number evaluates to itself
        2. A call expression evaluates to its arguments values combined by an operator
7. Interactive Interpreters
    1. Read-Eval-Print Loop
        1. Interactive interpreters
            1. Read text input from the user
            2. Parse the text input into an expression
            3. Evaluate the expression
            4. If any errors occur, report those errors, otherwise
            5. Print the value of the expression and repeat
8. Interpreting Scheme
    1. The Structure of an Interpreter
        1. Eval
            1. Base case: primitive values
            2. Recursive calls: 
                1. eval(operator, operands)
                2. Apply(procedure, arguments)
                3. Eval(sub-expressions) of special forms
        2. Apply
            1. Base cases
                1. Built-in primitive procedures
            2. Recursive Calls
                1. Eval(body) of user-defined procedures
        3. Mutual recursion among both functions
9. Special Forms
    1. The scheme_eval function choose behavior based on expression form
    2. Logical special forms
        1. logical forms may only evaluate some sub-expressions
10. Quotation
    1. Another special form
    2. The expression is not evaluated
11. Define Expressions