# Lecture 19 Scheme I

1. Questions
    1. How to keep track of parentheses?
2. Resources
    1. Page for built in functions
3. Scheme Expressions
    1. Operators always at the front
    2. Primitive expression: 2, 3.3, true, +, quotient
        1. Are self evaluating
        2. Plugging in 1 in the interpreter will just give us 1
    3. Combinations
        1. Combines things together somehow
        2. Things in parentheses means a combination
        3. (quotient 10 2)
    4. Call expressions include an operator and 0 or more operands in parentheses
        1. (quotient 10 2)
    5. Indentation
        1. Adding to the two things on the same indentations
    6. Built in functions
        1. (integer? 1.5)
            1. #t
    7. Built in boolean procedures
        1. (< 4 5)
            1. #t
        2. Usually something with a question mark will return a boolean
        3. The only falsy value is #f, everything else is truthy
            1. **0 is truthy in scheme**
4. Special Forms
    1. A combination that is not a call expression is a special form
    2. You just kinda have to learn them
    3. if expression: (if <predicate> <consequence> <alternative>
        1. if <truthy or falsey> <execute if true> <execute if false>
    4. Binding symboles: (define <symbol> <expression>)
    5. New procedures: (define (<symbol> <formal parameters>) <body>)
    6. Evaluation order
        1. Evaluate the predicate expression
        2. Evaluate either the consequent of alternative
5. Scheme Interpreters
    1. Similar to how python short circuits
    2. (and 1 2 3 4 5)
        1. 5
    3. Don’t need to wrap strings in quotes, only one at the beginning
        1. print ‘big
    4. use () to call a function
        1. Calling a Function x
        2. x vs (x)
6. Lambda Expressions
    1. Evaluates to anonymous procedures
    2. (lambda (<formal parameters>) <body>)
    3. ((define (f) 3))
        1. errors because we can’t call the string of f
    4. ((lambda () 3))
        1. 3
        2. this is ok
7. More special forms
    1. We either have to evaluate the function that we created or use a lambda for helper functions
    2. Cond & Begin
        1. Cond special form that behaves like if-elif-else statements in Python
        2. The begin special form combines multiple expressions into one expression
    3. Let Expressions
        1. binds symbols to values temporarily, just for one expression
8. Lists
    1. Scheme Lists
        1. **Everything in scheme list is a linked list**
        2. cons: two argument procedure that creates a linked list
        3. car: procudure that returns the first element of a list
        4. cds: procedure that return sth rest of a list
        5. nil: the empty list
        6. **Written in parentheses with elements separated by spaces**
    2. If we create a list in Scheme, it makes a linked list
        1. doesn’t evaluate nested, will include the operators
        2. will talk more about in interpreter lecture
9. Symbolic Programming
10. List Processing
11. Example: Even Subsets
    1. We use a lot of recursion ← No iteration
    2. We want the subsets that have an even sum
    3. Recursive approach: even subsets of s include:
        1. all the even subsets of the rest of s
        2. the first element of s followed by an (even/odd) subset of the rest
        3. just the first element of s if it is even
12.