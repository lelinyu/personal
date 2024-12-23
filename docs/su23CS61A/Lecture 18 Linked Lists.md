# Lecture 18 Linked Lists

1. Questions
2. Lists vs Linked Lists
    1. List is like a bus
    2. A linked list is like a train (more flexible and can expand)
3. Linked Lists
    1. Chain of objects where each object holds a **value and a reference to the next link**
    2. Linked list ends when the final reference is empty
4. Linked Lists Class
    1. L = Link(1, Link(2, Link(3)))
5. Mutating Linked Lists
    1. Attribute assignments can change first and rest attributes of a Link
    2. Using assignment statements to mutate a linked list
6. There can be infinite lists
    1. Setting the sublist as the linked list itself
    2. cyclic linked lists link back on themselves
7. Nested Linked Lists
    1. first can also be a linked list
8. Iteration with Linked Lists
    1. Linked lists are recursive data types and therefore lead to recursive implementations
        1. Using while loops
            1. Doing something with the first element: l.first
            2. Shift the pointer to the next node: l = l.rest
            3. While condition: l is not Link.empty
9. Implementing Functions

```python
def range_link(start, end)
	"""
	Making a function that returns a link containing consecutive integers from start to end
	not including end
	similar to how range works
	"""
	if start == end:
		return link.empty
	else:
		return link(start, range_link(start+1, end))

def map_link(f, ll):
	"""
	Returning a link that contains f(x) for each x in link ll
	"""
	if ll.rest is Link.empty:
		return link.empty
	else:
		return link(f(ll.first), map_link(f, ll.rest))

def filter_link(f, ll):
	"""
	Return a link that contains only the elements x of link ll
	for which f(x) is a true value
	"""
	if ll.rest is Link.empty:
		return Link.empty
	elif f(ll.first):
		return Link(ll.first, filter_link(f, ll.rest))
	else:
		return filter_link(f, ll.rest)
```

1. Linked Lists Operations
    1. Insert
        1. Linked lists require more space but provide faster insertion
    2. Delete
        1. No matter which node you want to delete, it takes one step:
        2. Point the rest of the node before the one to delete the one after
    3. Access
        1. I need to iterate through all the previous nodes using .rest
2. Comparing Operations
    1. Lists
        1. insert: linear
        2. append: constant, sometimes linear (depends on memory allocated)
        3. delete: linear
        4. find: linear
        5. access: constant
    2. Linked Lists
        1. insert: constant
        2. delete: constant
        3. find: linear
        4. access: linear
3. Linked List Exercises

```python
def ordered(s, key=lambda x:x)
	"""Is link s ordered"""
	if s.rest is Link.empty or s is Link.empty:
		return True
	elif key(s.first) > key(s.rest.first):
		return False
	else:
		ordered(s.rest, key)

def merge(s, t):
	""" 
	Return a sorted Link containing the eleemtns of sorted s & t
	"""
	if s is Link.empty:
		return s
	elif t is Link.empty:
		return t
	elif s.first < t.first:
		return Link(s.first, merge(s.rest, t))
	else:
		return Link(t.first, merge(s, t.rest)

def merge_in_place(s, t);
	"""Return sorted Link containing elements of sorted s & t"""
	if s is Link.empty:
		return s
	elif t is Link.empty:
		return t
	elif s.first < t.first:
		s.rest = merge_in_place(s.rest, t)
		return s
	else:
		t.rest = merge_in_place(s, t.rest)
		return t
```

1. Circular, Doubly Linked Lists
    1. Circular linked list → list looping back on itself
    2. With doubly linked list
        1. you can get the information about the link before and link after
        2. it has self.next
        3. also has self.prev