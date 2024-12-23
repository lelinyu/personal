# Lecture 17 Trees (class)

1. Questions
2. Trees
    1. Tree class definition
        1. self.branches is always a list of Tree objects
        2. Trees are recursive by nature
    2. Tree terminology
        1. If t is an instance of a tree
        2. Variable t is pointing at the root of our tree
        3. Individual tree objects contained within it known as nodes
    3. ADT Trees vs OOP Tree
        1. Know the differences
        2. OOP Tree is Capital letters for a class
        3. ADT Tree is lowercase for a method
    4. Accessing branches attribute
        1. Branches are a list of trees
        2. t.branches[0] ← to get the first branch
        3. t.branches[1].branches[2] ← Nested branches
    5. What is t.branches?
        1. **It is a list of tree objects, not Tree objects themselves**
    6. Tree processing
        1. Each Tree has
            1. A label
            2. 0 or more branches, which are themselves Trees
        2. Most of our algorithms to process trees are going to be recursive
3. Examples

Count Trees

```python
def count_leaves(t):
	if t.is_leaf():
		return 1
	else:
		sum = 0 
		for b in t.branches:
			sum += count_leaves(b)
		return sum
	#also able to do one line solution
	#return sum([counter_leaves(b) for b in t.branches])
```

List leaves

```python
#Returns a list of leaf labels of T

def list_leaves(t):
	if t.is_leaf():
		return [t.label]
	else:
		counter = []
		for b in t.branches:
			counter += list_leaves(b)
		return counter
		#two liner
		#list_of_lists = [list_leaves(b) for b in t.branches]
		#return sum(list_of_lists, start=[])
```

Count Paths

```python
def count_paths(t, total):
	counter = 0
	if total == t.label:
		counter += 1
	for b in t.branches:
		counter += count_paths(b, total-t.label)
	return counter

#Two liner
# found = int(t.label == total)
# return sum([count_paths(b, total-t.label) for b in t.branches]) + found
```

1. String Representation

```python
#prints the nodes of the tree with depth based indent
def print_tree(t):
	def helper(t, indent):
		print (indent * " " + str(t.label))
		for b in t.branches:
			helper(b, indent + 2) #2 is an arbitrary number, just the amt of indent we want
	helper(t, 0)

#If you need to carry information across recursive calls, use a helper function
```

1. there technically is no base case
    1. For loop doesn’t execute if branches is empty
        1. that is our unofficial base case
2. Mutating Trees

Mutates T such that every label is doubled

```python
#return value of this function is none
#should actually be mutating the tree

def double_mut(t):
	t.label *= 2
	for b in t.branches:
		double_mut(b)
```

1. Syntax Trees
    1. Syntax is the branch of linguistics that studies sentence structure
    2. Syntax Trees aim to model the structure of languages in a way that’s easy to visualized