# Lecture 12 Iterators and Generators

1. Questions
    1. why is map considered easily 
    2. how does the countdown function keep track of k
    3. Does yield skip to the next one?
2. Iterables
    1. objects (or data) that can be iterated over
    2. contains some elements in some order that can be kept track of by going from one element to the next; looped over
    3. Can i use it in a for loop or list comprehension?
        1. if yes, then it is an iterable
    4. Examples
        1. list
        2. string
        3. dictionary
        4. range
        5. tuple
        6. Iterators
3. Iterators
    1. Container can provide an iterator that provides access to its elements in order
    2. iter(iterable)
        1. return an iterator over the elements of an iterable value
    3. next(iterator)
        1. return the next element in an iterator
    4. If we start a new iterator, it starts from the beginning
    5. We error if we use iterable when there are no more elements
    6. Can pass iterator into a list
        1. interpreter returns the rest of the iterable’s values
    7. Arrow pointer is stored as an index
        1. if you get rid of elements, then the new index value is evaluated
    8. Iterators are like bookmarks
        1. An iterator is an iterable
4. Dictionary Iteration
    1. View of a Dictionary
        1. iterator returned from iter and can be passed to next;
        2. all iterators are mutable
    2. A dictionary, its keys, its values, and its items are all iterable values
        1. The order of items in a dictionary is the order in which they were added (Python 3.6+)
5. For Statements
    1. Can put iterators in a for loop
        1. will complete the iterator in a normal for loop
6. Built-in Iterator Functions
    1. Many results are computed lazily
        1. Only computed when needed
    2. Examples
        1. map(func, iterable)
            1. iterate over func(x) for x in iterable
        2. filter(func, iterable)
            1. iterate over x in iterable if func(x)
        3. zip(first_iter, second_iter):
        4. reversed(sequence)
            1. iterate over x in a sequence in reverse order
    3. To view the contents of an iterator, place the result elements into a container
        1. list(iterable)
        2. tuple(iterable)
        3. sorted(iterable)
    4. Map returns an iterator
        1. only computers when calling next on it
    5. Reversed doesnt auto compute reverse of t, only when you ask it to
7. The Zip Function
    1. Returns an iterator over co-indexed tuples
    2. Zip skips extra numbers
8. Using Iterators
    1. Reasons for Using Iterators
        1. Code that processes an iterator (via next) or iterable (via for or iter) makes few assumptions about the data itself
        2. useful for ensuring that each element of a sequence is processed only once
        3. limits the operations that can be performed on a sequence by only calling next
9. Generator
    1. special type of iterator
    2. Generators and Generator Functions
        1. can yield multiple values
        2. yield is like a return statement, but you can yield multiple values
        3. A generator function can yield multiple times
            1. generator is an iterator created automatically by calling a generator function
            2. generator functions when called, returns a generator that iterates over its yields
    3. All generators are iterators
        1. iterates through its yield statements
    4. Generator Functions can Yield from Iterables
        1. yield from statement yields all values from an iterator or iterable
        2. basically a for loop that yields all the values from a generator
    5. You can yield all values from recursive call with yield from
    6. Yielding Partitions
        1. 3