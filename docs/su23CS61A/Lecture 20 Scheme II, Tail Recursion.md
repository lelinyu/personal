# Lecture 20 Scheme II, Tail Recursion

1. Questions
2. Dynamic Scope
    1. Lexical scope - The way in which names are looked up in Scheme and Python
        1. Parents of a frame is the environment in which a procedure was defined
    2. Dynamic Scope
        1. The parent of a frame is the environment in which a procedure was called
3. Tail Recursion
    1. Functional Programming
        1. All functions are pure functions
        2. No re-assignment and no mutable data types
        3. Name-value bindings are permanent
        4. Advantages
            1. Value of an expression is independent of the order in which sub-expressions are evaluated
            2. Sub-expressions can safely be evaluated in parallel or only on demand (lazily)
            3. Referential transparency: value of an expression doesn’t change when we substitute one of its subexpression with the value of that subexpression
    2. Recursion and Iteration in Python
        1. Python recursive calls always create new active frames
    3. Tail recursion
        1. Making recursive functions more space efficient (constant space)
        2. Recursive functions in scheme should be tail recursive
        3. Factorial function
            1. Saving my value in the argument
            2. (factorial 6 1)
            3. (factorial 5 6)
            4. (factorial 4 30)
            5. …
            6. (factorial 1 720)
            7. 720
4. Tail Calls
    1. A procedure call that has not yet returned is active
    2. Scheme interpreter should support an unbounded number of active tail calls using only a constant amount of space
    3. A tail call is a call expression in a tail context:
        1. last body sub-expression in a lambda expression (or procedure definition)
        2. Sub expression 2 and 3 in a tail context if expression
        3. All non-predicate sub-expressions in a tail context cond
        4. Last sub expression in a tail context and, or, begin, or let
    4. Example: Length of a list
        1. Call expression is not a tail call if more computation is still required in the calling procedure
    5. Eval with Tail Call Optimization
5. Tail Recursion Examples
    1. Every parent function needs to be tail recursive
    2. If we need to do more computation after we do the recursive function then it isn’t tail recursive
6. Map and Reduce
    1. Take in an iterable
    2. Applies on every element in iterable
7. Implementing Tail Call Optimization
    1. Thunk - An expression wrapped in an argument-less function
    2. Trampolining
        1. A loop that iteratively invokes thunk-returning functions
        2. You’ll eventually get back an answer when you keep calling a function
            1. A trampoline will just keep calling until you get an answer
8. Scheme Practice
    1. Extra Tail Recursion Examples
        1.