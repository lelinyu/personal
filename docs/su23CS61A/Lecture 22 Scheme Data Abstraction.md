# Lecture 22 Scheme Data Abstraction

1. Questions
2. Data Abstraction
    1. Don’t need to know how things are implemented
    2. Only need to know what its behavior is
    3. Group - A scheme data abstraction
        1. (group first-val second-val)
        2. constructs a new group from 2 arguments
        3. Group basically groups values together
        4. 
    4. Note: Lists are not mutable in scheme
    5. Vocab
        1. Data Abstraction: groups compound information into units to be accessed and manipulated
        2. Constructor: a procedure that creates a data abstraction
        3. Selector: accesses and returns some information when a data abstraction is passed into it
        4. Documentation: information or instructions that describe how a data abstraction work
        5. Implementation: how something is coded behind the scenes
3. Abstraction Barrier
    1. Each layer only uses the layer below it
        1. User program
        2. Data Abstraction
        3. Primitive Representation