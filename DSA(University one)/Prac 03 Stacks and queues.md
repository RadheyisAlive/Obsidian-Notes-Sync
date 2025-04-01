  

```Python
import numpy as np


class Dsa_Stack():
    def __init__(self,size):
        self.size = size
        self.stack = np.empty(size,dtype=object)
        self.top = -1
        self.count = 0

    def isEmpty(self):
        return self.count == 0
    def isFull(self):
        return self.count == self.size  
    def push(self,value):
        if (self.isFull()==True):
            raise Exception ("no space left")
        else:
            self.top +=1
            self.stack[self.top] = value
            self.count +=1

    def pop(self):
        if (self.isEmpty()==True):
            raise Exception ("The array is empty")
        else:
            topval = self.stack[self.top]  # this is how we are accessing the top value from the stack array
            self.stack[self.top] = None      \#we are setting the top value of the array to none
            self.top -=1       # then we are setting the element before the top value which we had set to none, as the new top value.
            self.count -=1      # and decreased the count as well.
            return topval
        
class Dsa_Queue():
    def __init__(self, size):
        self.size = size
        self.queue = np.empty(size, dtype=object)
        self.count = 0

    def isEmpty(self):
        return self.count == 0

    def isFull(self):
        return self.count == self.size

class Shuffling_Queue(Dsa_Queue):
    def __init__(self, size):
        super().__init__(size)

    def enqueue(self, value):
        if self.isFull():
            raise Exception("The array is full")
        else:
            self.queue[self.count] = value
            self.count += 1

    def dequeue(self):
        if self.isEmpty():
            raise Exception("The array is empty")
        else:
            for i in range(len(self.queue) - 1):
                self.queue[i] = self.queue[i + 1]
            self.queue[self.count - 1] = None
            self.count -= 1

class CircularQueue(Dsa_Queue):
    def __init__(self, size):
        super().__init__(size)
        self.rear = -1
        self.front = -1

    def isEmpty(self):
        return self.front == -1 and self.rear == -1

    def enqueue(self, value):
        if self.isFull():
            raise Exception("The array is full")
        elif self.isEmpty():
            self.front = self.rear = 0
            self.queue[self.rear] = value
        else:
            self.rear = (self.rear + 1) % self.size     # selects the next available slot to input element, as we can only put in the end of the queue so, it will point towards the next to the previous rear.
            self.queue[self.rear] = value

    def dequeue(self):
        if self.isEmpty():
            raise Exception("The array is Empty")
        elif self.rear == self.front:                      \#This checks if the queue is having only one element.
            value = self.queue[self.front]
            self.rear = self.front = -1    # we putting the rear and front back to the position as they were declared in the empty array.
            return value
        else:
            value = self.queue[self.front]  
            self.front = (self.front + 1) % self.size       # this will dequeue the starting from the first element and then the front will point to the next element of the element dequeue, which means ignoring the first element, and pointing to the element next to it.
            return value

    def Output(self):
        if self.isEmpty():
            print("Queue is empty")
        else:
            if self.front <= self.rear:     # checks if the array wraps around or not
                print("The array is :", self.queue[self.front:self.rear + 1])        # then prints the elements from front till rear
            else:
                print("The array is :", self.queue[self.front:] + self.queue[:self.rear + 1])      # then it concatenates


stack = Dsa_Stack(5)
stack.push("Name")
stack.push(20)
stack.push(30)
stack.push(40)
stack.push(50)
print("The elements before pop are:",stack.stack)
stack.pop()
print("The new elements after pop are:",stack.stack)

shuffling_queue = Shuffling_Queue(5)
shuffling_queue.enqueue(10)
shuffling_queue.enqueue(20)
shuffling_queue.enqueue(30)
shuffling_queue.enqueue(40)
shuffling_queue.enqueue(50)
print("The array by shuffling_queue before dequeue is :", shuffling_queue.queue)
shuffling_queue.dequeue()
print("The array by shuffling_queue after dequeue  is  :", shuffling_queue.queue)
circular_queue = CircularQueue(5)
circular_queue.enqueue(5)
circular_queue.enqueue(3)
circular_queue.enqueue(6)
circular_queue.enqueue(7)
print("the array by circular_queue before dequeue is:", circular_queue.queue)
circular_queue.dequeue()
print("the array by circular_queue after dequeue is:", circular_queue.queue)
circular_queue.Output()

```

### How `super()` Works in Your Code

Let's look at the `Shuffling_Queue` and `CircularQueue` classes in your code:

```Python
python
Copy code
class Shuffling_Queue(Dsa_Queue):
    def __init__(self, size):
        super().__init__(size)

```

Here, `super()` is used in the `__init__()` method of the `Shuffling_Queue` class to call the `__init__()` method of its parent class `Dsa_Queue`. This means that when you create an instance of `Shuffling_Queue`, the initialization code of `Dsa_Queue` is executed, setting up the `size` and `queue` attributes.

Similarly, in the `CircularQueue` class:

```Python
python
Copy code
class CircularQueue(Dsa_Queue):
    def __init__(self, size):
        super().__init__(size)
        self.rear = -1
        self.front = -1

```

Again, `super()` is used to call the `__init__()` method of `Dsa_Queue`, initializing the `size` and `queue` attributes. After this, additional attributes specific to the `CircularQueue` class (`rear` and `front`) are initialized.

### Key Benefits of Using `super()`:

1. **Code Reusability**: You don't need to rewrite the code from the parent class in the child class. For example, you avoid duplicating the code that initializes `size` and `queue`.
2. **Maintenance**: If you update the parent class's `__init__()` method, all child classes that use `super()` will automatically get the updated behavior.
3. **Multiple Inheritance Compatibility**: `super()` handles method resolution order (MRO) automatically, making it easier to work with complex inheritance structures.

  

## This is to understand the circular and shuffling queue in this program it is a good program it will make you understand every concept of stacks and queues

  

Linear queues and shuffling queues (or shifting queues) share some similarities, but they have distinct differences in their implementation and behavior. Let's go over each concept to clarify.

### Linear Queue

- **Definition**: A linear queue is a straightforward implementation of the queue data structure where elements are arranged in a linear order.
- **Operations**:
    - **Enqueue**: Adds an element at the rear of the queue.
    - **Dequeue**: Removes an element from the front of the queue.
- **Structure**: Typically implemented using an array or linked list. In an array implementation, the front and rear pointers are moved forward with each operation.
- **Limitation**: After multiple enqueues and dequeues, the front index moves forward, which can result in unused space at the beginning of the array.

**Example**:

```Plain
plaintext
Copy code
Enqueue: [10, 20, 30, 40, 50]
After Dequeue: [None, 20, 30, 40, 50]

```

### Shuffling Queue (Shifting Queue)

- **Definition**: A shuffling or shifting queue is similar to a linear queue, but when an element is dequeued, all remaining elements are shifted forward to fill the gap left at the front.
- **Operations**:
    - **Enqueue**: Adds an element at the end of the queue.
    - **Dequeue**: Removes the front element and then shifts all subsequent elements one position to the left.
- **Structure**: Often implemented using an array. The elements are moved to ensure that the first position in the array is always the front of the queue.
- **Advantage**: It ensures no wasted space in the array.
- **Disadvantage**: The shifting operation can be costly in terms of time complexity, as it requires moving all elements forward after each dequeue.

**Example**:

```Plain
plaintext
Copy code
Enqueue: [10, 20, 30, 40, 50]
After Dequeue and Shift: [20, 30, 40, 50, None]

```

### Similarities

1. **FIFO Principle**: Both linear and shuffling queues follow the First-In-First-Out (FIFO) principle, where the first element added is the first one to be removed.
2. **Operations**: Both support `enqueue` and `dequeue` operations.

### Differences

1. **Space Utilization**:
    - **Linear Queue**: May have wasted space if not managed properly (due to the front pointer moving forward).
    - **Shuffling Queue**: No wasted space as elements are shifted to fill any gaps.
2. **Time Complexity**:
    - **Linear Queue**: `Enqueue` and `dequeue` operations are `O(1)` as long as there is space.
    - **Shuffling Queue**: `Dequeue` is `O(n)` because it requires shifting elements, where `n` is the number of elements in the queue.
3. **Implementation Complexity**:
    - **Linear Queue**: Easier to implement but requires careful handling of space.
    - **Shuffling Queue**: More complex due to the shifting mechanism but eliminates wasted space.

### Conclusion

While linear and shuffling queues have similar goals and follow the same FIFO logic, they differ significantly in how they handle space and time complexity, especially concerning the `dequeue` operation.