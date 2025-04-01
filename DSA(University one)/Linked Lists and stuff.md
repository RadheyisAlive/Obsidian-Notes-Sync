A simple linked list is a collection of nodes where each node contains a piece of data and a reference (or link) to the next node in the sequence. It is like a chain where each link (node) knows the address of the next link. Here’s a basic explanation and a simple implementation in Python:

### Basic Concept

1. **Node**: Each element in the linked list is called a node. A node has two parts:
    - **Data**: The value that the node holds.
    - **Next**: A pointer to the next node in the list.
2. **Linked List**: A collection of nodes where the first node is called the `head`. Each node points to the next node, and the last node points to `None`, indicating the end of the list.

### Implementation in Python

Here's a simple implementation of a singly linked list with basic operations like adding a node and displaying the list.

```Python
# Definition of the Node class
class DSAListNode:
    def __init__(self, inValue):
        self.value = inValue  # Value of the node
        self.next = None      # Reference to the next node in the list

    # Accessor method to get the value
    def getValue(self):
        return self.value

    # Mutator method to set the value
    def setValue(self, inValue):
        self.value = inValue

    # Accessor method to get the next node
    def getNext(self):
        return self.next

    # Mutator method to set the next node
    def setNext(self, newNext):
        self.next = newNext

# Definition of the LinkedList class
class DSALinkedList:
    def __init__(self):
        self.head = None  # Head of the list

    # Method to check if the list is empty
    def isEmpty(self):
        return self.head is None

    # Method to insert a node at the beginning of the list
    def insertFirst(self, newValue):
        newNd = DSAListNode(newValue)  # Create a new node
        if self.isEmpty():
            self.head = newNd  # If list is empty, set the head to new node
        else:
            newNd.setNext(self.head)  # Set new node's next to current head
            self.head = newNd          # Update head to new node

    # Method to insert a node at the end of the list
    def insertLast(self, newValue):
        newNd = DSAListNode(newValue)  # Create a new node
        if self.isEmpty():
            self.head = newNd  # If list is empty, set the head to new node
        else:
            currNd = self.head
            # Traverse to the end of the list
            while currNd.getNext() is not None:
                currNd = currNd.getNext()
            currNd.setNext(newNd)  # Set the last node's next to new node

    # Method to get the value of the first node
    def peekFirst(self):
        if self.isEmpty():
            raise Exception("List is empty")
        else:
            return self.head.getValue()

    # Method to get the value of the last node
    def peekLast(self):
        if self.isEmpty():
            raise Exception("List is empty")
        else:
            currNd = self.head
            # Traverse to the end of the list
            while currNd.getNext() is not None:
                currNd = currNd.getNext()
            return currNd.getValue()

    # Method to remove the first node and return its value
    def removeFirst(self):
        if self.isEmpty():
            raise Exception("List is empty")
        else:
            nodeValue = self.head.getValue()
            self.head = self.head.getNext()  # Move head to the next node
            return nodeValue

    # Method to remove the last node and return its value
    def removeLast(self):
        if self.isEmpty():
            raise Exception("List is empty")
        elif self.head.getNext() is None:  # Only one node in the list
            nodeValue = self.head.getValue()
            self.head = None  # List becomes empty
            return nodeValue
        else:
            prevNd = None
            currNd = self.head
            # Traverse to the second-last node
            while currNd.getNext() is not None:
                prevNd = currNd
                currNd = currNd.getNext()
            prevNd.setNext(None)  # Remove reference to the last node
            return currNd.getValue()  # Return the value of the removed node

# Example usage of the linked list:
if __name__ == "__main__":
    myList = DSALinkedList()
    
    # Insert nodes into the list
    myList.insertFirst(10)
    myList.insertFirst(20)
    myList.insertLast(30)
    
    # Display first and last values
    print("First Value:", myList.peekFirst())  # Should print 20
    print("Last Value:", myList.peekLast())    # Should print 30
    
    # Remove first and last nodes and display their values
    print("Removed First Value:", myList.removeFirst())  # Should print 20
    print("Removed Last Value:", myList.removeLast())    # Should print 30
g
```

### Explaination

### 1. **DSAListNode Class**

This class defines a single node in a linked list. Each node stores some data (`value`) and a reference (`next`) to the next node in the list.

```Python
python
Copy code
class DSAListNode:
    def __init__(self, inValue):
        self.value = inValue  # The value or data of the node
        self.next = None      # The reference to the next node in the list

```

- `**__init__(self, inValue)**`: The constructor method is called when you create a new node. It initializes the `value` with the provided `inValue` and sets `next` to `None`, indicating that there is no next node yet.

```Python
python
Copy code
    def getValue(self):
        return self.value

```

- `**getValue()**`: This is an accessor method that returns the value stored in the node.

```Python
python
Copy code
    def setValue(self, inValue):
        self.value = inValue

```

- `**setValue(inValue)**`: This is a mutator method that sets the value of the node to `inValue`.

```Python
python
Copy code
    def getNext(self):
        return self.next

```

- `**getNext()**`: This is an accessor method that returns the reference (or pointer) to the next node in the list.

```Python
python
Copy code
    def setNext(self, newNext):
        self.next = newNext

```

- `**setNext(newNext)**`: This is a mutator method that sets the reference to the next node to `newNext`.

### 2. **DSALinkedList Class**

This class defines a linked list, which is a collection of `DSAListNode` nodes linked together. It includes methods to manage and manipulate the linked list.

```Python
python
Copy code
class DSALinkedList:
    def __init__(self):
        self.head = None  # The head or start of the list, initially set to None

```

- `**__init__()**`: This is the constructor for the linked list. It initializes `head` to `None`, indicating that the list is empty when created.

```Python
python
Copy code
    def isEmpty(self):
        return self.head is None

```

- `**isEmpty()**`: This method checks if the linked list is empty by seeing if `head` is `None`. It returns `True` if the list is empty and `False` otherwise.

```Python
python
Copy code
    def insertFirst(self, newValue):
        newNd = DSAListNode(newValue)  # Create a new node with the value
        if self.isEmpty():
            self.head = newNd  # If the list is empty, set the head to the new node
        else:
            newNd.setNext(self.head)  # Set new node's next to current head
            self.head = newNd          # Update head to the new node

```

- `**insertFirst(newValue)**`: This method inserts a new node at the beginning of the list.
    - It creates a new node (`newNd`) with the value `newValue`.
    - If the list is empty (`isEmpty()` returns `True`), it sets `head` to `newNd`.
    - If the list is not empty, it sets the `next` of `newNd` to the current `head` and then updates `head` to `newNd`.

```Python
python
Copy code
    def insertLast(self, newValue):
        newNd = DSAListNode(newValue)  # Create a new node with the value
        if self.isEmpty():
            self.head = newNd  # If the list is empty, set the head to the new node
        else:
            currNd = self.head
            while currNd.getNext() is not None:  # Traverse to the last node
                currNd = currNd.getNext()
            currNd.setNext(newNd)  # Set the next of the last node to new node

```

- `**insertLast(newValue)**`: This method inserts a new node at the end of the list.
    - It creates a new node (`newNd`) with the value `newValue`.
    - If the list is empty, it sets `head` to `newNd`.
    - If the list is not empty, it traverses to the last node (`currNd`) using a loop and then sets `currNd.next` to `newNd`.

```Python
python
Copy code
    def peekFirst(self):
        if self.isEmpty():
            raise Exception("List is empty")  # Raise an exception if list is empty
        else:
            return self.head.getValue()  # Return the value of the first node

```

- `**peekFirst()**`: This method returns the value of the first node without removing it.
    - It raises an exception if the list is empty.
    - Otherwise, it returns the value of the `head` node.

```Python
python
Copy code
    def peekLast(self):
        if self.isEmpty():
            raise Exception("List is empty")  # Raise an exception if list is empty
        else:
            currNd = self.head
            while currNd.getNext() is not None:  # Traverse to the last node
                currNd = currNd.getNext()
            return currNd.getValue()  # Return the value of the last node

```

- `**peekLast()**`: This method returns the value of the last node without removing it.
    - It raises an exception if the list is empty.
    - It traverses the list to find the last node and returns its value.

```Python
python
Copy code
    def removeFirst(self):
        if self.isEmpty():
            raise Exception("List is empty")  # Raise an exception if list is empty
        else:
            nodeValue = self.head.getValue()  # Store value of the head node
            self.head = self.head.getNext()  # Move head to the next node
            return nodeValue  # Return the value of the removed node

```

- `**removeFirst()**`: This method removes the first node and returns its value.
    - It raises an exception if the list is empty.
    - It stores the value of the `head` node, updates `head` to `head.next`, and returns the stored value.

```Python
python
Copy code
    def removeLast(self):
        if self.isEmpty():
            raise Exception("List is empty")  # Raise an exception if list is empty
        elif self.head.getNext() is None:  # Only one node in the list
            nodeValue = self.head.getValue()
            self.head = None  # List becomes empty
            return nodeValue
        else:
            prevNd = None
            currNd = self.head
            while currNd.getNext() is not None:  # Traverse to the second-last node
                prevNd = currNd
                currNd = currNd.getNext()
            prevNd.setNext(None)  # Remove reference to the last node
            return currNd.getValue()  # Return the value of the removed node

```

- `**removeLast()**`: This method removes the last node and returns its value.
    - It raises an exception if the list is empty.
    - If there is only one node, it removes it by setting `head` to `None`.
    - Otherwise, it traverses to the second-last node (`prevNd`) and removes the last node by setting `prevNd.next` to `None`.

### 3. **Example Usage**

This part demonstrates how to use the linked list. It adds nodes, peeks at the first and last values, and removes nodes:

```Python
python
Copy code
if __name__ == "__main__":
    myList = DSALinkedList()  # Create an empty linked list

    # Insert nodes into the list
    myList.insertFirst(10)
    myList.insertFirst(20)
    myList.insertLast(30)

    # Display first and last values
    print("First Value:", myList.peekFirst())  # Should print 20
    print("Last Value:", myList.peekLast())    # Should print 30

    # Remove first and last nodes and display their values
    print("Removed First Value:", myList.removeFirst())  # Should print 20
    print("Removed Last Value:", myList.removeLast())    # Should print 30

```

### Summary

- `**DSAListNode**` **Class**: Represents individual nodes with a value and a pointer to the next node.
- `**DSALinkedList**` **Class**: Manages the list of nodes, supports insertion/removal of nodes at the beginning or end, and provides methods to access node values.
- **Example Usage**: Demonstrates the functionality of adding, accessing, and removing nodes in the linked list.

This implementation provides a basic framework for working with a singly linked list in Python.

As compared to array what is the disadvantage of Traversing linked list

Traversing Linked Lists  
• Only the first node is available directly (via head)  
• Thus getting to a particular node requires that we traverse from the head  
(first) node, through all the next pointers until we reach the desired node  
• This obviously can be pretty slow  
• Compare this to an array, which can get to any element in one step  
• via a little bit of arithmetic – it works because the array elements are all stored in a  
contiguous block  
• But linked lists aren’t contiguous, so we have to do traversing  
• This is the main disadvantage of linked lists: access time