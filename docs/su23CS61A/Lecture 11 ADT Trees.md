# Lecture 11 ADT Trees

1. Questions
    1. Why doesn’t increment and double do infinite recursion if there is no base case? 11:40am
2. Trees
    1. Recursive description
        1. A tree has a root label and a list of branches
        2. Each branch is a tree
        3. Tree with zero branches is a leaf (no lines going downward)
    2. Relative description (family trees)
        1. Each location in a tree is called a node (a circle)
        2. Each node has a label that can be any value
        3. One node can be the parent/child of another
        4. The top node is the root node
    3. Path
        1. series of node and edges connecting the tree
    4. Implementing the Tree Abstraction
        1. a tree has a root label and a list of branches
        2. Each branch is a tree
            1. Branches must be trees
            2. Use tree constructor when creating branches
        3. Functions
            1. double function
                1. applying a function to all the values in the tree
3. Tree Processing
    1. Creating Trees
        1. Putting a recursive function into a list comprehension
    2. tree Processing Uses Recursion
        1. List of leaf labels for each branch
            1. still gives back a list of leaves
4. Tree Representation
    1. can use print_tree
    2. draw() ← at code.cs61a.org
5. Example: Counting Paths
6. Memoization
    1. Recursive Computation of the Fibonacci Sequence
        1. A lot of the recursion is repeated
        2. We can store recursion values to be used later
            1. Cache → dictionary that stores our values
            2. keys are the function calls
            3. store results in dictionary
        3.