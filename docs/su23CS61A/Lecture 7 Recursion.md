# Lecture 7 Recursion

1. Question
    1. Going over how the Luhn Sum function works
    2. sum_digits_rec, still unsure about how it works
2. Analogy - Place in Line
    1. Ask the person in front, how many people are in front of you
3. Recursive Functions
    1. A function is called recursive if the body of that function calls itself, either directly or indirectly
    2. May require applying that function
4. Recursive Call Structure
    1. Base case(s)
        1. simplest instance of the problem can be solved without much work
        2. the trueism - no other work needed
        3. The first person knows their first in line
    2. Recursive Call
        1. making a call to the same function with a smaller input
        2. How many people in front of you?
    3. Recombination
        1. Using the result of the recursive call to solve the original problem
5. Example: Factorial
    1. To solve Factorial of 5, solve factorial of 4 * 5
    2. Base cases
        1. think about the edges of our domain
6. Example: Sum Digits
    1. We can break the problem of summing the digits of 2023 into a smaller instance of the same problem, plus extra stuff
    2. Solving 2023
        1. sum_digits(202) + 3
    3. Use a split function to help
        1. returns the number split into parts
    4. Anatomy of a Recursive Function
        1. Def statement header is similar to other functions
        2. Conditional statements check for base cases
            1. base cases evaluated without recursive calls
        3. Recursive cases are evaluated with recursive calls
7. Recursion in Environment Diagrams
    1. Every time you call a function you open a new frame
8. Iteration vs Recursion
    1. Recursion
        1. keep track of value in the arguments of the function
9. Verifying Recursive Functions
    1. The Recursive Leap of Faith
        1. Is fact implemented correctly?
            1. Verify the base case
            2. Treat fact as a functional abstraction
            3. Assume that fact(n-1) is correct
            4. Verify that fact(n) is correct
10. Mutual Recursion
    1. The Luhn Algorithm
        1. Rightmost digit, check digits moving left, doubling each number, sum #s > 10’s digits
        2. Take the sum of all digits
    2. Two functions calling each other
        1. Luhn sum calls luhn sum double
        2. Luhn sum double calls Luhn sum
11. More Examples
    1. Implementing a Function
        1. Read the description
        2. Verify the examples and pick a simple one
        3. Read the template
        4. Annotate names with values from your chosen example
        5. Write code to compute the result
    2. Remove function
        1. base case: 0
12. Converting Recursion to Iteration
    1. Figure out what state must be maintained by the iterative function
13. Summary
    1. Anatomy of Recursive functions
        1. base case
        2. recursive case
        3. recombination
    2. Mutual recursion
    3. Relationship between iteration and recursion
    4. Implementing recursive functions