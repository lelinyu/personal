# Lecture 16 Inheritance and String Representation

1. Questions
    1. Repr will print quotes
    2. Calling on interpreter will not
        1. calling interpreter on obj equvialent to
        2. obj = print(repr(obj))
    3. str(obj) = obj.__str__()
        1. when using str, use the class of the object that is being used
2. Review
    1. Attributes
        1. all objects have attributes
        2. name-value pairs
        3. Classes are objects too, so they have attributes
        4. Instance attribute: attribute of an instance
        5. Class attribute: attribute of the class of an instance
    2. Looking up attributes by name
        1. <expression>.<name>
    3. Class attributes
        1. “shared” across all instances of a class
    4. Attribute Assignment
        1. If the object is an instance, then assignment sets an instance attribute
        2. If the object is a class, then assignment sets a class attribute
3. Inheritance
    1. relating classes together
    2. Specialized class may have the same attributes as the general class, along with some special case behavior
    3. Example: Checking Account
        1. Two options for withdrawing
        2. super()
            1. creates a temporary object of the parent account
    4. Looking up attribute names on classes
        1. Base class attributes aren’t copied into subclasses
        2. Looking up a name in a class
            1. If it names an attribute in the class, return the attribute value
            2. Otherwise, look up the name in the base class, if there is one
        3. Modifying the class attribute in the base class, affects the child class
    5. Class Relationships
        1. You can make a child class of a child class
    6. Class Hierarchy
        1. Account
            1. Checking Account, Savings Account
                1. SuperSaverAccount
4. Object-Oriented Design
    1. Don’t need to repeat ourselves if we just use existing implementations
    2. Inheritance and Composition
        1. Inheritance is best for representing is-a relationships
            1. A checking account is a specific type of account
            2. Checking Account inherits from Account
5. Multiple Inheritance
    1. Can inherit multiple classes
    2. Methods come from the different parents of the As Seen on TV Account
    3. If methods overlap
        1. Look left to right to see who has precedence
        2. Left has priority
6. Representation
    1. String Representations
        1. An object value should behave like the kind of data it is meant to represent
        2. In python all objects produce two string representations
            1. The str is legible to humans
            2. the repr is legible to the Python Interpreter
    2. repr String for an Object
        1. repr(object) → string
        2. It returns the string to return the object
        3. The result of calling repr on a value is what Python prints in an interactive session
        4. Some objects do not have a simple Python-readable string
            1. >>>repr(min)
            2. ‘<built in function-min>’
    3. str String representation for an Object
        1. Human interpretable strings are useful as well
        2. str gives a more human readable version
        3. Result of calling str on the value of an expression is what Python prints using the “print” function

```python
>>> repr(half)
'Fraction(1,2)'
>>>str(half)
'1/2'
```

1. F-Strings
    1. String Interpolation in Python
        1. evaluating a string literal that contains expresssions
        2. Putting brackets around our string to display the value
    2. Result of evaluating an f-string literatal contains the str value of each subexpression
    
    ```python
    >>> f"add 1 + 2 = {1 + 2}"
    'add 1 + 2 = 3'
    ```
    

```python
Making our own str and repr

def __str__(self):
	return f"Holder: {self.holder}\nBalance: {self.balance}"

def __repr__(self):
	return f"Account('{self.holder}')"

#print result has the actual result
#str(a) is the actual string it self, so the \n is not honored
```