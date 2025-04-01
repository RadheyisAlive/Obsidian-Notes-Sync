  

Yes, that's correct! "queues " is a data structure concept or terminology, not a built-in function or class in Python.

### What is a Queue in Data Structure?

A queue is a linear data structure that follows the First In, First Out (FIFO) principle. This means that the first element added to the queue will be the first one to be removed, similar to a line of people waiting for service.

### Basic Operations of a Queue:

1. **Enqueue:** Adds an element to the end of the queue.
2. **Dequeue:** Removes and returns the element from the front of the queue.
3. **Front/Peek:** Returns the front element without removing it.
4. **isEmpty:** Checks if the queue has no elements.
5. **Size:** Returns the number of elements in the queue.

Here’s a simple implementation of a queue using Python:

```Python
python
Copy code
# Define a Queue class
class Queue:
    def __init__(self):
        # Initialize an empty list to store queue elements
        self.queue = []

    def enqueue(self, item):
        # Add an item to the end of the queue
        self.queue.append(item)
        print(f"Item {item} enqueued to the queue.")

    def dequeue(self):
        # Remove and return the front item from the queue
        if not self.is_empty():
            removed_item = self.queue.pop(0)
            print(f"Item {removed_item} dequeued from the queue.")
            return removed_item
        else:
            print("Queue is empty. Cannot dequeue an item.")
            return None

    def peek(self):
        # Return the front item without removing it
        if not self.is_empty():
            print(f"Front item is {self.queue[0]}.")
            return self.queue[0]
        else:
            print("Queue is empty. No front item to show.")
            return None

    def is_empty(self):
        # Check if the queue is empty
        return len(self.queue) == 0

    def size(self):
        # Return the number of items in the queue
        print(f"Queue size is {len(self.queue)}.")
        return len(self.queue)

# Example usage:
my_queue = Queue()

my_queue.enqueue(10)  # Output: Item 10 enqueued to the queue.
my_queue.enqueue(20)  # Output: Item 20 enqueued to the queue.
my_queue.enqueue(30)  # Output: Item 30 enqueued to the queue.

my_queue.peek()       # Output: Front item is 10.

my_queue.dequeue()    # Output: Item 10 dequeued from the queue.
my_queue.dequeue()    # Output: Item 20 dequeued from the queue.

my_queue.size()       # Output: Queue size is 1.

my_queue.dequeue()    # Output: Item 30 dequeued from the queue.
my_queue.dequeue()    # Output: Queue is empty. Cannot dequeue an item.

```

### What Do Queues Store?

Queues, like stacks, can store any type of data depending on the implementation and use case. The most common data types stored in a queue include:

1. **Primitive Data Types:**
    - **Integers:** For storing numbers like 1, 2, 3, etc.
    - **Floats:** For storing decimal numbers like 3.14, 2.718, etc.
    - **Characters:** For storing individual letters, symbols, etc.
    - **Booleans:** For storing true/false values.
2. **Complex Data Types:**
    - **Strings:** For storing sequences of characters like "hello", "world", etc.
    - **Lists/Arrays:** For storing multiple values in an ordered collection.
    - **Tuples:** For storing ordered collections of different data types.
    - **Dictionaries:** For storing key-value pairs.
3. **Custom Objects:**
    - You can store instances of custom classes or objects that you define in your code. This is useful in more complex applications, where you want to store objects with multiple attributes and methods.
4. **Pointers/References:**
    - In some languages, a queue can store references or pointers to other data structures or objects. This is common in languages like C/C++.

### Examples of Queue Usage:

1. **Task Scheduling:** Managing tasks in a sequential order, such as print jobs in a printer queue.
2. **Breadth-First Search (BFS):** Using a queue to explore nodes level by level in graph traversal algorithms.
3. **Order Processing:** Managing orders in the sequence they are received and processed.
4. **Customer Service:** Managing people waiting in line to be served, like in a ticket counter.

### Example in Python:

```Python
python
Copy code
# Queue storing different data types
class Queue:
    def __init__(self):
        self.queue = []

    def enqueue(self, item):
        self.queue.append(item)

    def dequeue(self):
        if not self.is_empty():
            return self.queue.pop(0)
        else:
            return None

    def is_empty(self):
        return len(self.queue) == 0

# Creating a queue instance
my_queue = Queue()

# Enqueuing different types of data onto the queue
my_queue.enqueue(42)            # Integer
my_queue.enqueue(3.14)          # Float
my_queue.enqueue("hello")       # String
my_queue.enqueue([1, 2, 3])     # List
my_queue.enqueue({'a': 1, 'b': 2}) # Dictionary

# Dequeuing elements and displaying them
print(my_queue.dequeue())  # Output: 42
print(my_queue.dequeue())  # Output: 3.14
print(my_queue.dequeue())  # Output: "hello"
print(my_queue.dequeue())  # Output: [1, 2, 3]
print(my_queue.dequeue())  # Output: {'a': 1, 'b': 2}

```

In this example, the queue stores different data types and the `dequeue` method returns the elements in the order they were added, demonstrating the FIFO behavior of queues.

[[Types of Queues]]