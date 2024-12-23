# Lecture 26 Special Topics 1 (Compilers and CPython Internals)

1. Questions
2. Review
    1. Levels of Languages
        1. High-level Language
        2. Assembly Language
        3. Machine Language
    2. Programming Languages
        1. Machine languages
            1. fixed set of instructions invoke operations implemented by the circuitry of the CPU
            2. Operations refer to specific hardware memory addresses, no abstraction
        2. High level languages
            1. Abstraction
    3. Compilers
        1. translate source code into machine code so that the machine code can be distributed and run repeatedly 
    4. Interpreters 
        1. run source code directly producing an output/value, without first compiling it into machine code
3. Understanding Source Code
    1. parser must be written to understand that source code
    2. parser creates an Abstract Syntax Tree (AST)
        1. AST is passed through an evaluator
4. Parsing
    1. Takes in text and returns an expression that represents the text in a tree-like structure
    2. Lexical analysis
        1. Tells us if it accept valid characters
        2. such as python new lines
        3. converts input text into a list of tokens
        4. Each token represents the smallest unit of information
    3. Syntactic analysis
        1. With the tokens, creating a tree for evaluating
        2. identifies the hierarchical structure of an expression
        3. Symbols can be nested
5. BNF
    1. Backaus-Naur Form is a scheme designed specifically for describing the syntax of programming languages using context-free-grammars
        1. CFG can be parsed statement by statement without needing prior context
        2. In python, to evaluate a line, we don’t really need to know the lines before it
    2. BNF can tell us how to make the AST
6. AST
    1. represents the hierarchical structure of formal languages
    2. They 
        1. are unambiguous
        2. can be annotated
        3. can hold additional information about code
        4. are typically built by the parser
7. Parsing Python
    1. How does the program know that we only used one line of code?
        1. Inspect - module that has functions to get information about live objects such as classes, functions, frames, etc.
        2. Ast - module to help process trees of the Python abstract syntax grammar
    2. Dangling Else (Variation)
        1. What does this evaluate to?
            1. >>>1 if 2 else 3 if False else 5
                1. 1
8. Interpreted vs Compiled
    1. Who’s interpreting who?
        1. Big snek
        2. Our Python is interpreted by C
9. CPython Internals
    1. runs byte code directly producing an output/value but first compiles source code into byte code
    2. Compiled AST into byte code, then interpret Python
10. Generating Byte Code
    1. Dis module
        1. disassembling python code in Python bytecode
        2. Byte code compiler can automatically multiply before assigning value to variable
11. Stacks
    1. Stack - data strcuture for storing and retrieving values. Can only retrieve the most recently added item
        1. Push - adds an item to the top
        2. Pop - removes an item at the top and returns it
        3. Peek - looks at the item at the top without removing it
    2. Stack Machine
        1. a processor or virtual machine that computes by modifying values in a stack
        2. Operator - combines the top two values in the stack and then pushes the result
    3.