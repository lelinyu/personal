# Lecture 13 Efficiency

1. Questions
2. Measuring efficiency
    1. How much resource consumption a computation task takes
    2. We are concerned with time and space efficiency
    3. Time efficiency
        1. how long to wait
    4. Memory Efficiency
        1. how much memory running your application takes
3. Orders of Growth
    1. Prepend
        1. Adding something to the end of a list
4. Exponentiation
    1. We don’t really care about the values, more that the computation is linear
    2. Logarithmic exponentiation
    3. Quadratic Time
    4. Exponential Time
5. Common Orders of Growth
    1. Exponential growth
        1. fibonaci
    2. Quadratic
        1. overlap
    3. Linear
        1. slow exp
    4. Logarithmic growth
        1. exp_fast
    5. Constant growth
        1. increasing n doesn’t affect time
6. Order of Growth Notation
    1. Big Theta and Big O Notation for Orders of Growth
        1. BigO represents the worst case
            1. O(b^n)
            2. O(n^2)
            3. O(log n)
        2. Big Theta is average case
7. Space Usage
    1. Space and Environments
        1. At any moment, there is a set of active environments
        2. Values and frame in active environments consume memory
            1. We can close frames once we know their return value
        3. Space consumption
            1. The longest path (depth) of the tree of fib
    2. Generators are lazy
        1. They save space when we use them because they don’t need to compute everything
    3.