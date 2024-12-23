# Lecture 8 Tree Recursion

1. Questions
    1. Can we draw a tree structure for recursion that isn’t specifically tree recursion?
        1. Would it just be one branch?
2. Order of Recursive Calls
    1. Pickup where you left off on the previous function
    2. Each cascade frame is from a different call to cascade
        1. Until the return value appear, call has not been completed yet
    3. Put the base cases first in recursive functions
        1. base case - smallest case in your problem
3. Tree Recursion
    1. Tree-shaped processes arise whenever executing the body of a recursive function makes more than one recursive call
    2. A Tree-Recursive Process
        1. The computational process of fib evolves into a tree structure
    3. Repetition in Tree-Recursive Computation
        1. Fibonacci sequence isn’t super efficient as many values are calculated many times
    4. Recursive vs Iterative
        1. Recursive
            1. Visually represents recursive definition
            2. Computation happens in many frames
        2. Iterative
            1. Easy to follow calculations
            2. Computation in one frame
4. Example: Counting Partitions
    1. The number of partitions of a positive integer n, using parts up to size m, is the number of ways in which n can be expressed as the sum of positive integer parts up to m in increasing order
    2. No duplicates for combinations
    3. Example:
        1. counter_partitions(6,4)
            1. 2 + 4 = 6
    4. Recursive Decomposition
        1. finding simpler instances of the problem
        2. Explore two possibilities:
            1. Use at least one 4
            2. Don’t use any 4
        3. Solve two simpler problems
            1. Use at least one 4
                1. After you use 4, then it becomes count_partitions(2,4)
            2. Don’t use any 4
                1. If you don’t use 4, then it becomes count_partitions(6,3)
        
        ```python
        def count_partitions(n,m):
        	if n==0:
        		return 1
        	elif n<0: #failure case: overshooting
        		return 0
        	elif m==0: #failure case: there is no possible values for m when it is 0
        		return 0
        	else:
        		with_m = counter_partitions(n-m, m)
        		without_m = count_partitions(n, m-1)
        		return with_m + without_m
        ```
        
        1. Tree recursion
            1. multiple recursive calls within its body, each modeling a specific decision
            2. base cases may not always be apparent, and sometimes working through recursive calls can help you figure them out