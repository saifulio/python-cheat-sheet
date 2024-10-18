# Basic Syntax

## 1. Variables and Data Types

```python
# Integer

x = 5

# Float

y = 3.14

# String

name = "Python"

# Boolean

is_valid = True
```

## 2. Basic Operations

```python
# Arithmetic Operators
a = 5 + 3   # 8
b = 5 - 2   # 3
c = 5 * 2   # 10
d = 5 / 2   # 2.5

# Modulus and Exponentiation
e = 5 % 2   # 1 (Remainder)
f = 2 ** 3  # 8 (Exponentiation)

# Comparison Operators
g = 5 > 3   # True
h = 5 == 5  # True
```

## 3. Lists

```python
fruits = ["apple", "banana", "cherry"]
fruits.append("orange")    # Add item
fruits.remove("banana")    # Remove item
print(fruits[0])           # Access first item
```

## 4. Dictionaries

```python

person = {"name": "Alice", "age": 25}
print(person["name"])       # Access by key
person["city"] = "New York" # Add key-value pair
```

## 5. Conditionals

```python

if x > 10:
    print("x is greater than 10")
elif x == 10:
    print("x is 10")
else:
    print("x is less than 10")
```

## 6. Loops

```python

# For loop
for i in range(5):
    print(i)

# While loop
count = 0
while count < 5:
    print(count)
    count += 1
```

## 7. Functions

```python

def greet(name):
    return f"Hello, {name}!"

print(greet("Alice"))
```

## 8. Classes and Objects

```python

class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def bark(self):
        return "Woof!"

dog = Dog("Buddy", 5)
print(dog.bark())          # Outputs: Woof!
```

## 9. File Handling

```python

# Writing to a file
with open("file.txt", "w") as file:
    file.write("Hello, World!")

# Reading from a file
with open("file.txt", "r") as file:
    content = file.read()
    print(content)
```

## 10. Error Handling

```python

try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
finally:
    print("This runs no matter what.")
```

# Data Structures

## 1. Lists (Dynamic Arrays)

```python
# Creating a list
my_list = [1, 2, 3, 4, 5]

# Access elements
print(my_list[0])    # Output: 1

# Append elements
my_list.append(6)

# Remove elements
my_list.remove(3)    # Removes the first occurrence of 3

# Slicing
sub_list = my_list[1:3]  # [2, 4]

# Iterating
for item in my_list:
    print(item)
```

## 2. Tuples (Immutable)

```python
# Creating a tuple
my_tuple = (1, 2, 3)

# Access elements
print(my_tuple[0])    # Output: 1

# Tuples are immutable, so no modification allowed
```

## 3. Dictionaries (Hash Maps)

```python
# Creating a dictionary
my_dict = {"name": "Alice", "age": 25}

# Access elements
print(my_dict["name"])    # Output: Alice

# Add/Update key-value pairs
my_dict["city"] = "New York"

# Remove a key-value pair
del my_dict["age"]

# Iterating through keys and values
for key, value in my_dict.items():
    print(f"{key}: {value}")
```

## 4. Sets (Unordered, No Duplicates)

```python
# Creating a set
my_set = {1, 2, 3, 3, 4}

# Add an element
my_set.add(5)

# Remove an element
my_set.remove(2)

# Set operations
set1 = {1, 2, 3}
set2 = {3, 4, 5}
union = set1 | set2          # {1, 2, 3, 4, 5}
intersection = set1 & set2   # {3}
difference = set1 - set2     # {1, 2}
5. Stacks (LIFO)
python
Copy code
# Using a list as a stack
stack = []

# Push
stack.append(10)

# Pop
stack.pop()    # Removes and returns last element (LIFO)

# Peek at top element
top = stack[-1] if stack else None
```

## 6. Queues (FIFO)

```python
from collections import deque

# Using deque as a queue
queue = deque()

# Enqueue
queue.append(10)

# Dequeue
queue.popleft()    # Removes and returns the first element (FIFO)
```

## 7. Priority Queues (Heaps)

```python
import heapq

# Create a heap (min-heap by default)
heap = [1, 3, 5, 7]
heapq.heapify(heap)

# Push (Insert element in heap)
heapq.heappush(heap, 2)

# Pop (Remove the smallest element)
heapq.heappop(heap)
```

## 8. Linked Lists

Python doesn’t have built-in linked lists, but you can implement one:

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
        else:
            current = self.head
            while current.next:
                current = current.next
            current.next = new_node

# Usage
ll = LinkedList()
ll.append(1)
ll.append(2)
```

## 9. Graphs

```python
# Representing graph using adjacency list
graph = {
    'A': ['B', 'C'],
    'B': ['A', 'D'],
    'C': ['A', 'D'],
    'D': ['B', 'C']
}

# DFS (Depth First Search)
def dfs(graph, node, visited=set()):
    if node not in visited:
        print(node)
        visited.add(node)
        for neighbor in graph[node]:
            dfs(graph, neighbor, visited)

# BFS (Breadth First Search)
from collections import deque
def bfs(graph, start):
    visited = set()
    queue = deque([start])
    while queue:
        node = queue.popleft()
        if node not in visited:
            print(node)
            visited.add(node)
            queue.extend(graph[node])

# Usage
dfs(graph, 'A')
bfs(graph, 'A')
```

## 10. Binary Trees

```python
class TreeNode:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

# Example of Binary Tree Traversal
def inorder_traversal(root):
    if root:
        inorder_traversal(root.left)
        print(root.value)
        inorder_traversal(root.right)

# Usage
root = TreeNode(1)
root.left = TreeNode(2)
root.right = TreeNode(3)
inorder_traversal(root)  # Output: 2 1 3
```

## 11. Binary Search Tree (BST)

```python
class BST:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

    def insert(self, value):
        if value < self.value:
            if self.left:
                self.left.insert(value)
            else:
                self.left = BST(value)
        elif value > self.value:
            if self.right:
                self.right.insert(value)
            else:
                self.right = BST(value)

    def search(self, value):
        if value == self.value:
            return True
        elif value < self.value and self.left:
            return self.left.search(value)
        elif value > self.value and self.right:
            return self.right.search(value)
        return False

# Usage
root = BST(10)
root.insert(5)
root.insert(15)
print(root.search(15))  # Output: True
```
