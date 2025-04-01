Perfect video for understanding circular and linear queues, Love you mallu teachers

[https://youtu.be/-VzzjEBhbEk?si=KoETpbR3pCHVcJ2z](https://youtu.be/-VzzjEBhbEk?si=KoETpbR3pCHVcJ2z)

### Types of Queues in Data Structure

1. **Simple Queue (Linear Queue):**
    - **Definition:** A basic form of queue that follows the First In, First Out (FIFO) principle. Elements are added at the rear (end) and removed from the front (beginning).
    - **Example Implementation in Python:**
        
        ```Python
        python
        Copy code
        class SimpleQueue:
            def __init__(self):
                self.queue = []
        
            def enqueue(self, item):
                self.queue.append(item)
        
            def dequeue(self):
                if not self.is_empty():
                    return self.queue.pop(0)
        \#The pop() method removes the element at the specified position. Syntax list.pop(pos)
                else:
                    print("Queue is empty!")
                    return None
        
            def is_empty(self):
                return len(self.queue) == 0
        
            def peek(self):
                if not self.is_empty():
                    return self.queue[0]
                else:
                    print("Queue is empty!")
                    return None
        
            def size(self):
                return len(self.queue)
        
        # Usage
        q = SimpleQueue()
        q.enqueue(1)
        q.enqueue(2)
        print(q.dequeue())  # Output: 1
        print(q.peek())     # Output: 2
        
        ```
        
    - **What It Stores:** Like all queues, it can store any data type, such as integers, strings, lists, etc.
2. **Circular Queue:**
    - **Definition:** A queue in which the last position is connected back to the first position, forming a circle. This helps in utilizing space efficiently, avoiding the "false overflow" problem.
    - **Example Implementation in Python:**
        
        ```Python
        python
        Copy code
        class CircularQueue:
            def __init__(self, capacity):
                self.queue = [None] * capacity
                self.capacity = capacity
                self.front = self.rear = -1
        
            def enqueue(self, item):
                if (self.rear + 1) % self.capacity == self.front:
                    print("Queue is full!")
                elif self.front == -1:
                    self.front = 0
                    self.rear = 0
                    self.queue[self.rear] = item
                else:
                    self.rear = (self.rear + 1) % self.capacity
                    self.queue[self.rear] = item
        
            def dequeue(self):
                if self.front == -1:
                    print("Queue is empty!")
                    return None
                elif self.front == self.rear:
                    item = self.queue[self.front]
                    self.front = self.rear = -1
                    return item
                else:
                    item = self.queue[self.front]
                    self.front = (self.front + 1) % self.capacity
                    return item
        
            def is_empty(self):
                return self.front == -1
        
            def peek(self):
                if self.is_empty():
                    return None
                else:
                    return self.queue[self.front]
        
            def size(self):
                if self.is_empty():
                    return 0
                elif self.rear >= self.front:
                    return self.rear - self.front + 1
                else:
                    return self.capacity - self.front + self.rear + 1
        
        # Usage
        cq = CircularQueue(3)
        cq.enqueue(1)
        cq.enqueue(2)
        print(cq.dequeue())  # Output: 1
        print(cq.peek())     # Output: 2
        
        ```
        
    - **What It Stores:** Like a simple queue, it can store any data type, such as numbers, strings, and objects.
3. **Priority Queue:**
    - **Definition:** A queue where each element has a priority. Elements with higher priority are dequeued before elements with lower priority, regardless of their insertion order.
    - **Example Implementation in Python:**
        
        ```Python
        python
        Copy code
        import heapq
        
        class PriorityQueue:
            def __init__(self):
                self.queue = []
        
            def enqueue(self, item, priority):
                heapq.heappush(self.queue, (priority, item))
        
            def dequeue(self):
                if not self.is_empty():
                    return heapq.heappop(self.queue)[1]
                else:
                    print("Queue is empty!")
                    return None
        
            def is_empty(self):
                return len(self.queue) == 0
        
            def peek(self):
                if self.is_empty():
                    return None
                else:
                    return self.queue[0][1]
        
            def size(self):
                return len(self.queue)
        
        # Usage
        pq = PriorityQueue()
        pq.enqueue("task1", 2)  # lower number means higher priority
        pq.enqueue("task2", 1)
        pq.enqueue("task3", 3)
        print(pq.dequeue())  # Output: task2 (highest priority)
        print(pq.peek())     # Output: task1
        
        ```
        
    - **What It Stores:** It stores elements along with their priority. The data can be of any type (e.g., strings representing tasks) and is associated with a priority value (typically a number).
4. **Double-Ended Queue (Deque):**
    - **Definition:** A queue where elements can be added or removed from both the front and the rear. It combines the features of both stacks and queues.
    - **Example Implementation in Python:**
        
        ```Python
        python
        Copy code
        from collections import deque
        
        class Deque:
            def __init__(self):
                self.deque = deque()
        
            def add_front(self, item):
                self.deque.appendleft(item)
        
            def add_rear(self, item):
                self.deque.append(item)
        
            def remove_front(self):
                if not self.is_empty():
                    return self.deque.popleft()
                else:
                    print("Deque is empty!")
                    return None
        
            def remove_rear(self):
                if not self.is_empty():
                    return self.deque.pop()
                else:
                    print("Deque is empty!")
                    return None
        
            def is_empty(self):
                return len(self.deque) == 0
        
            def peek_front(self):
                if self.is_empty():
                    return None
                else:
                    return self.deque[0]
        
            def peek_rear(self):
                if self.is_empty():
                    return None
                else:
                    return self.deque[-1]
        
            def size(self):
                return len(self.deque)
        
        # Usage
        dq = Deque()
        dq.add_rear(10)
        dq.add_front(20)
        print(dq.peek_front())  # Output: 20
        print(dq.remove_front())  # Output: 20
        print(dq.peek_rear())  # Output: 10
        
        ```
        
    - **What It Stores:** It can store any data type, such as integers, strings, or objects, and allows access from both ends.

### Summary

- **Simple Queue:** Follows FIFO, elements added to the rear, removed from the front.
- **Circular Queue:** A circular version of the simple queue, efficiently utilizing space.
- **Priority Queue:** Elements are dequeued based on priority rather than insertion order.
- **Double-Ended Queue (Deque):** Allows addition and removal of elements from both ends.

These different types of queues serve specific needs in various applications like task scheduling, CPU job scheduling, and real-time event handling.