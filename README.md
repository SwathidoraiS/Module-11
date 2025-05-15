# 📚 Doubly Linked List: Insert Elements at the End of a Doubly Linked List

This Python program demonstrates the creation and manipulation of a **Doubly Linked List** where elements can be inserted at the **end** of the list. The program also provides a method to traverse the list and display the elements.

---

## 🎯 Aim

To write a Python program that:
- Implements a **Doubly Linked List**.
- Allows insertion of elements at the end of the list.
- Provides functionality to traverse the list and display its elements.

---

## 🧠 Algorithm

1. **Step 1:** Define a class `Node` to represent each node in the doubly linked list with attributes:
   - `item` for storing the data of the node.
   - `nref` for storing the reference to the next node.
   - `pref` for storing the reference to the previous node.

2. **Step 2:** Define a class `DoublyLinkedList` with:
   - `start_node` to point to the first node of the list.

3. **Step 3:** Define methods in the `DoublyLinkedList` class:
   - `insert_in_emptylist(data)` to insert an element when the list is empty.
   - `insert_at_end(data)` to insert elements at the end of the list.
   - `traverse_list()` to traverse the list and print the elements.

4. **Step 4:** Create an instance of `DoublyLinkedList` and use the `insert_at_end()` method to insert elements into the list.

5. **Step 5:** Use the `traverse_list()` method to print the elements of the list.

---

## 💻 Program
~~~c
class Node:
    def __init__(self, data):
        self.data = data
        self.prev = None
        self.next = None

class DoublyLinkedList:
    def __init__(self):
        self.head = None
    def insert_at_end(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        last_node = self.head
        while last_node.next:
            last_node = last_node.next
        last_node.next = new_node
        new_node.prev = last_node
    def traverse(self):
        current_node = self.head
        if not current_node:
            print("The list is empty.")
            return
        print("Doubly Linked List:")
        while current_node:
            print(current_node.data, end=" <-> " if current_node.next else "")
            current_node = current_node.next
        print()
dll = DoublyLinkedList()
n = int(input("Enter the number of elements you want to insert: "))
for i in range(n):
    value = input(f"Enter value {i + 1}: ")
    dll.insert_at_end(value)
dll.traverse()
~~~

## Sample Output
![Screenshot 2025-05-11 161733](https://github.com/user-attachments/assets/2263449d-f15a-4e8c-a85b-49f4939ba119)

## Result

Thus the program has been executed successfully.

# 📝 Doubly Linked List: Search an Element

This Python program demonstrates the implementation of a **Doubly Linked List** where you can insert elements at both the beginning and the end of the list. Additionally, it allows you to search for a specific element in the list.

---

## 🎯 Aim

To write a Python program that:
- Implements a **Doubly Linked List** with functions to insert elements at the beginning and the end of the list.
- Implements a search function to check if a given element exists in the list.

---

## 🧠 Algorithm

1. **Step 1:** Define a class `Nodeq` with:
   - `data` to store the node's value.
   - `next` to store the reference to the next node.
   - `prev` to store the reference to the previous node.

2. **Step 2:** Define a class `DoublyLinkedList` with:
   - `head` to point to the first node.

3. **Step 3:** In the `DoublyLinkedList` class, define methods:
   - `insert_beginning(data)` to insert a node at the beginning.
   - `insert_end(data)` to insert a node at the end.
   - `search(data)` to search for an element in the list.

4. **Step 4:** Create an instance of `DoublyLinkedList`.
   - Insert elements at the beginning and end.
   - Search for specific elements.

---

## 💻 Program
~~~c
class Node:
    def __init__(self, data):
        self.data = data
        self.prev = None
        self.next = None
class DoublyLinkedList:
    def __init__(self):
        self.head = None
    def insert_at_beginning(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
        else:
            new_node.next = self.head
            self.head.prev = new_node
            self.head = new_node
    def insert_at_end(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        last_node = self.head
        while last_node.next:
            last_node = last_node.next
        last_node.next = new_node
        new_node.prev = last_node
    def search(self, key):
        current_node = self.head
        while current_node:
            if current_node.data == key:
                return True
            current_node = current_node.next
        return False
    def traverse(self):
        current_node = self.head
        if not current_node:
            print("The list is empty.")
            return
        print("Doubly Linked List:")
        while current_node:
            print(current_node.data, end=" <-> " if current_node.next else "")
            current_node = current_node.next
        print()
dll = DoublyLinkedList()
n = int(input("Enter the number of elements you want to insert: "))
for i in range(n):
    value = input(f"Enter value {i + 1} to insert at the beginning: ")
    dll.insert_at_beginning(value)
for i in range(n):
    value = input(f"Enter value {i + 1} to insert at the end: ")
    dll.insert_at_end(value)
dll.traverse()
search_key = input("Enter the element you want to search for: ")
if dll.search(search_key):
    print(f"The element '{search_key}' is present in the list.")
else:
    print(f"The element '{search_key}' is not present in the list.")
~~~

## Sample Output
![Screenshot 2025-05-11 162135](https://github.com/user-attachments/assets/9ce9e806-7a3d-45fa-ad09-20c14b754dbf)

## Result
Thus the program has been executed successfully.

# 📚 Singly Linked List : Find the Middle Node of a Singly Linked List Using Recursion

This Python program demonstrates how to find the middle node of a singly linked list using recursion. The program calculates the middle element by utilizing two pointers, with one pointer moving one step at a time (slow) and the other moving two steps at a time (fast). When the fast pointer reaches the end of the list, the slow pointer will be at the middle node.

## 🎯 Aim

To write a Python program that:
- Creates a singly linked list.
- Uses recursion to find the middle node of the list.
- In case of an even number of nodes, it returns the second middle element.

## 🧠 Algorithm

1. **Node Class**: 
   - Define a `Node` class to represent each node in the singly linked list. Each node has two attributes: `data` and `next`.
   
2. **LinkedList Class**:
   - Define a `LinkedList` class that manages the linked list with methods to:
     - `append(data)`: Add a new node to the end of the list.
     - `get_middle_recursive(slow, fast)`: A recursive helper function to find the middle node using two pointers (slow and fast).
     - `find_middle()`: A method to call the recursive function and return the middle node's data.

3. **Input**:
   - First, the program reads an integer `n`, representing the number of elements in the linked list.
   - Then, it reads `n` space-separated integers to form the linked list.

4. **Recursive Middle Finding**:
   - The `get_middle_recursive` method uses two pointers to traverse the list:
     - The `slow` pointer moves one step at a time.
     - The `fast` pointer moves two steps at a time.
   - When the `fast` pointer reaches the end, the `slow` pointer will be at the middle node.

5. **Output**:
   - The program prints the middle element. If the list has an even number of nodes, it returns the second middle element.

---

## 💻 Program
~~~c
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
class SinglyLinkedList:
    def __init__(self):
        self.head = None
    def append(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        curr = self.head
        while curr.next:
            curr = curr.next
        curr.next = new_node
    def display(self):
        current = self.head
        print("Singly Linked List:")
        while current:
            print(current.data, end=" -> " if current.next else "")
            current = current.next
        print()
def find_middle_recursive(slow, fast):
    if not fast or not fast.next:
        return slow
    return find_middle_recursive(slow.next, fast.next.next)
sll = SinglyLinkedList()
n = int(input("Enter the number of elements in the list: "))
for i in range(n):
    value = input(f"Enter value {i + 1}: ")
    sll.append(value)
sll.display()
if sll.head:
    middle_node = find_middle_recursive(sll.head, sll.head)
    print(f"\nMiddle node: {middle_node.data}")
else:
    print("The list is empty.")
~~~

## Sample Input & Output
![Screenshot 2025-05-11 162440](https://github.com/user-attachments/assets/cddaad05-bebe-479e-9da0-df85a62ff457)

## Result
Thus the program has been executed successfully.

# # 🔍 Singly Linked List-To Search an Element in a Linked List

This project contains a simple implementation of a **singly linked list** in Python, allowing insertion and searching of elements.

---

## 🎯 Aim

To write a Python program to search for a given element in a singly linked list using object-oriented programming principles.

---

## 🧠 Algorithm

1. **Define a Node class** with `data` and `next` attributes.
2. **Define a LinkedList class** with:
   - A `head` pointer initialized to `None`.
   - A `push()` method to add elements at the beginning.
   - A `search()` method to check whether a given value exists.
3. Create a `LinkedList` instance.
4. Insert the elements **10, 30, 11, 21, 14** using `push()` (which results in reverse order).
5. Read an integer input from the user.
6. Use `search()` to check if the element exists in the list.
7. Output **"Yes"** if found, else **"No"**.

---

## 💻 Program
~~~c
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class SinglyLinkedList:
    def __init__(self):
        self.head = None
    def insert(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        current = self.head
        while current.next:
            current = current.next
        current.next = new_node
    def display(self):
        if not self.head:
            print("The list is empty.")
            return
        current = self.head
        print("Singly Linked List:")
        while current:
            print(current.data, end=" -> " if current.next else "")
            current = current.next
        print()
    def search(self, key):
        current = self.head
        position = 0
        while current:
            if current.data == key:
                return position
            current = current.next
            position += 1
        return -1
sll = SinglyLinkedList()
n = int(input("Enter number of elements to insert: "))
for i in range(n):
    value = input(f"Enter element {i + 1}: ")
    sll.insert(value)
sll.display()
key = input("Enter the element to search for: ")
position = sll.search(key)
if position != -1:
    print(f"The element '{key}' was found at position {position}.")
else:
    print(f"The element '{key}' was not found in the list.")
~~~
## Sample Output
![Screenshot 2025-05-11 162740](https://github.com/user-attachments/assets/afe0bd42-0e01-4bbc-94e2-fced76c3db1c)

## Result
Thus the program has been executed successfully.

# 📝 Singly Linked List: Add Element at the Start

This Python program demonstrates the implementation of a **Singly Linked List** where a new element can be added at the **start** of the list.

---

## 🎯 Aim

To write a Python program that adds a **new element** at the **start** of a singly linked list. The program implements a `push_front` method that inserts an element at the front of the list, followed by a method to print the list.

---

## 🧠 Algorithm

1. **Step 1:** Define a class `Node` with:
   - `data` to store the node's value.
   - `next` to store the reference to the next node.
   
2. **Step 2:** Define a class `LinkedList` with:
   - `head` to point to the first node.
   
3. **Step 3:** In the `LinkedList` class, define a method `push_front(newElement)`:
   - Create a new node with `newElement`.
   - Set the new node's next pointer to the current head node.
   - Set the head to the new node.

4. **Step 4:** Define a method `PrintList()` to display the list:
   - Print the elements of the list or display "The list is empty." if the list is empty.

5. **Step 5:** Instantiate a `LinkedList` object, `MyList`, and add elements at the start using the `push_front()` method.

6. **Step 6:** Call the `PrintList()` method to display the list.

---

## Program
~~~c
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class SinglyLinkedList:
    def __init__(self):
        self.head = None
    def push_front(self, data):
        new_node = Node(data)
        new_node.next = self.head
        self.head = new_node
    def display(self):
        if not self.head:
            print("The list is empty.")
            return
        current = self.head
        print("Singly Linked List:")
        while current:
            print(current.data, end=" -> " if current.next else "")
            current = current.next
        print()
sll = SinglyLinkedList()
n = int(input("Enter number of elements to insert at the start: "))
for i in range(n):
    value = input(f"Enter element {i + 1}: ")
    sll.push_front(value)
sll.display()
~~~
## Sample Output

![Screenshot 2025-05-11 163014](https://github.com/user-attachments/assets/c3036749-13e7-4177-b125-a6beac123305)

## Result
Thus the program has been executed successfully.
