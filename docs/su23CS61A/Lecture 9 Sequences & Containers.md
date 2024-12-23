# Lecture 9 Sequences & Containers

1. Questions
    1. Is a key of a dictionary an index?
2. Sequences
    1. ordered collection of values
    2. different types
        1. strings - “hello world”
        2. lists - [1, “a”, 2, “b”]
            1. can be any data type
        3. ranges - range(0,10)
            1. sequence of numbers
3. Strings
    1. Strings are abstraction
        1. Representing data
        2. Representing language
        3. Representing programs
            1. can just put syntax into strings
        4. Single and Double quotes are equivalent
4. Lists
    1. Container that holds a sequence of values of any data type
    2. Empty list
        1. l = []
    3. List can hold any python value, separated by commas
        1. Able to hold functions as well
    4. Creating Lists
        1. nums = [2, 81, 16]
        2. We can also put call expression into our lists
        3. calc = [min(2,3), square(9,9)]
        
        ```python
        >>> calc
        [2, 81]
        
        #lists will evaluate things inside
        ```
        
    5. List Lengths
        1. “len” function computes the length of a list
    6. Indexing Lists
        1. Indexes start at 0
        2. Able to access an item by putting square brackets [] around it
            1. getitem(<list>, <index>
        3. Negative indexing starts from back of list
            1. [-1] returns the last index
    7. Concatenation and Repetition
        1. Can only concatenate a list with a list
        2. Multiplying *2 doubles the list and etc.
    8. List Slicing
        1. Passing 3 arguments
        2. list[<start index> : <end index> : <optional: step size> ]
            1. does not include end index
        3. Reversing a list
            1. Use a negative step size
            2. s[::1]
    9. Nested Lists
        1. Can have lists in a list
        2. “len” won’t go through nested items
            1. items separated by commas
5. Box and Pointer Notation (similar to environment diagram)
    1. creating a copy of a list
        1. c = a[:]
            1. slicing creates a copy
            2. a new list
    2. Reversing
        1. We look at the original indexes to reverse
        2. Starting index should be larger than ending index
            1. Step size is -1, we are working backward
    3. In environment diagrams
        1. Lists are represented as a row of index-labeled adjacent boxes
        2. each box either contains a primitive value or points to compound value
    4. Strings as Sequences
        1. Strings can also be sliced, concatenated
        2. classes[:5]
            1. Remember that it slices up to but not including the number
6. Containers
    1. Sequence is a type of container where we have elements in order
    2. Built in operator for testing whether an element appear in a compound value
        1. “not in” and “in”
        
        ```python
        >>>digits = [1,8,2,8]
        >>>1 in digits
        True
        ```
        
7. For Statements
    1. For statement execution procedure
    
    ```python
    for <name> in <expression>:
    	<suite>
    ```
    
    1. Evaluate the header<expression>, which must yield an iterable value (a sequence)
    2. For each element in that sequence, in order:
        1. Bind <name> to that element in the current frame
        2. Execute the <suite>
    3. Sequence Unpacking in For Statements
        1. 
        
        ```python
        pairs = [[1,2], [2,2]]
        
        for x, y in pairs:
        	x == y:
        		same_count += 1
        
        ```
        
8. Ranges
    1. Range function creates a sequence of consecutive integers
    2. range(<start>, <end>, <optional: skip>)
        1. Non-inclusive for end value
        2. inclusive for start value
    3. list(range(4)
        1. [0,1,2,3]
9. List Comprehensions
    1. Can have a for loop that can do an operation
    
    ```python
    [<map exp> for <name> in <iter exp> if <filter exp>]
    
    [<map exp> for <name> in <iter exp>]
    ```
    
    1. Combined expression that evaluates to a list using this evaluation procedure
        1. Add a new frame with the current frame as its parent
        2. Create empty result list that is the value of the expression
        3. For each element in the iterable value of <iter exp>:
            1. Bind <name> to that element in the new frame from step 1
            2. If <filter exp> evaluates to a true value, then add the values of <map exp> to resulting list
10. Aggregation
    1. Build-in functions take iterable arguments and aggregate them into a value
    2. sum()
        1. sums a list’
    3. max()
        1. maximum character in a string
        2. maximum number in a list
        3. key applies the function to the items in the list
    4. min()
    5. all()
        1. returns whether all the numbers in the list are truthy
11. Dictionaries
    1. Limitations on Dictionaries
        1. Dictionaries are collections of key-value pairs
        2. Dictionary keys do have two restrictions:
            1. A key of a dictionary cannot be a list or a dictionary (or any mutable type)
12. Summary
    1. Containers (lists and dictionaries) can store sequences of values
    2. List slicing creates a new list
    3. We can iterate over sequences using for statements
        1. Can be more concise than while statements
    4. List comprehension allows us to return a new list using values of an existing list
    5. Memoization makes computing more efficient