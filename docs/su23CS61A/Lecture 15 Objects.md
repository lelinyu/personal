# Lecture 15 Objects

1. Questions
2. Object-Oriented Programming
    1. A method for organizing programs
        1. Data Abstraction
        2. Bundling together info and related behavior
    2. Computation using distributed state
        1. Each object has its own local state
        2. Each object also knows how to manage its own local state, based on method calls
        3. Method calls are messages passed between objects
        4. Different types may relate to each other
3. Classes
    1. A class describes the general behavior of its instances
4. Class vs Objects
    1. A class combines and abstracts data and functions
    2. An object is an instantiation of a class
5. Class Statements
    1. The Class Statement
        1. Note: By convention, class names start with a capital letter
        2. Class statement creates a new class and bines that class to <name> in the first frame of the current environment
        3. Assignment and def statements in <suite> create attributes of the class
    
    ```python
    class <name>:
    	<suite>
    	color = 'red'
    	windows = 2
    ```
    
    1. When a class is called
        1. A new instance of that class is created:
        2. The __init__ method of the class is called with the new object as its first argument (named self), along with any additional arguments provided in the call expression
        3. What is self?
            1. references the object that you are trying to create
            2. technically binds self to what you bind the object to
    2. Object identity
        1. Every object that is an instance of a user-defined class has a unique identity
        2. Identity operators “is’ and “is not” test if two expressions evaluate to the same object
6. Methods
    1. Methods
        1. Functions defined in the suite of a class statement
        2. **self should always be bound to an instance of the Account class**
            1. We need to know which account to apply the method on
    2. Invoking Methods
        1. All invoked methods have access to the object via the self parameter, and so they can all access and manipulate the object’s state
        2. Dot notation automatically supplies the first argument to a method
            1. tom_account.deposit(100)
            2. ^ “tom_account” technically being passed into self
    3. Dot expressions
        1. Objects receive messages via dot notation
        2. dot notation accesses attributes of the instance or its class
        3. <expression>.<name>
            1. <expression> can be any valid Python expression
            2. <name> is probably more simple
            3. Evaluates to the value of the attribute looked up by <name> in the object that is the value of the <expression>
7. Attributes
    1. Accessing Attributes
        1. Using getattr, we can look up an attribute using a string
        2. getattr(tom_account, ‘balance’)
            1. passing in the object and the attribute you want to look up
        3. hasattr, searches if attribute exists
        4. Looking up an attribute name in an object may return
            1. one of its instance attributes
            2. one of the class attributes
    2. Methods and Functions
        1. Python distinguishes between:
            1. Functions
                1. Function: all arguments within parentheses
            2. Bound methods, which couple together a function and the object on which that method will be invoked
                1. Method: One object in the front and the rest of the args afte
            3. Object + Function = Bound Method
        2. Looking up Attributes by name
            1. To evaluate a dot expression:
                1. Evaluate the <expression> to the left of the dot, which yields the object of the dot expression
                2. <name> is matched against the instance attributes of that object; if an attribute with that name exists, its value is returned
                3. It not, <name> is looked up in the class, which yields a class attribute value
                4. That value is returned unless it is a function, in which case a bound method is returned instead
    3. Class Attributes
        1. “shared’ across all instances of a class because they are attributes of the class, not he instance
        2. By convention, class attributes defined before the constructor
8. Example: Bouncing Balls
    1. Ball Instance
        1. Allocate memory for a Ball object
        2. Initilialize the Ball object with values
        3. Return the Ball object
    2. Ball Class
        1. Making multiple Ball instances
9. Multi-class programs
    1. Usually need more than one class of objects in our program to model its complexity
    2. Face, eye, nose
        1. All different classes