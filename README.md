# Linked List in C++

##  Overview
A **linked list** is a **dynamic linear data structure** where elements, called **nodes**, are connected using **pointers**. Unlike arrays, linked lists do not require contiguous memory allocation, allowing for efficient insertion and deletion of elements at any position without the need to shift other elements.  

Key characteristics of linked lists:
- Each node contains **data** and a **pointer** to the next node.  
- The first node is called the **head**, and the last node typically points to `NULL` (or to the head in circular linked lists).  
- Linked lists can grow or shrink dynamically during program execution.  

Linked lists are widely used in applications where **flexible memory management** and **efficient insertion/deletion** are required, such as stacks, queues, dynamic memory allocation, and graph representations.

---

##  Theory

###  Structure of a Node
Each node in a linked list typically contains:
1. **Data** – stores the actual value of the node.  
2. **Next Pointer** – points to the next node in the sequence.

###  Types of Linked Lists

1. **Singly Linked List**  
   - Each node contains data and a pointer to the **next node** only.  
   - Traversal is **one-way** (from head to tail).  
   - Example structure in C++:
   ```cpp
   struct Node {
       int data;
       Node* next;
   };
   ```


2. ** Doubly Linked List
- Each node contains **three parts**:  
  1. **Data** – stores the actual value.  
  2. **Next Pointer** – points to the next node in the sequence.  
  3. **Previous Pointer** – points to the previous node in the sequence.  

- Traversal can be done in **both directions**: forward (head → tail) and backward (tail → head).  
- Provides more flexibility compared to a singly linked list but requires **extra memory** for the `prev` pointer.  

**Structure in C++:**
```cpp
struct Node {
    int data;
    Node* next;
    Node* prev;
};
```

3. **Circular Linked List
- In a **circular linked list**, the last node does not point to `NULL`.  
- Instead, it points back to the **first node**, forming a circular structure.  
- Traversal can begin at any node and continue until the same node is reached again.  
- Can be implemented as:  
  - **Singly Circular Linked List** – where the last node points to the head.  
  - **Doubly Circular Linked List** – where the last node points to the head and the head’s `prev` points to the tail.  

---

### 🔹 Operations on Linked Lists

1. **Creation**  
   - Initialize a linked list by creating nodes dynamically and linking them together.  

2. **Traversal**  
   - Visit each node starting from the head and process (e.g., display) the data.  

3. **Insertion**  
   - Add a new node at:  
     - The beginning  
     - The end  
     - A specific position  

4. **Deletion**  
   - Remove a node from:  
     - The beginning  
     - The end  
     - A specific position  

5. **Searching**  
   - Traverse the list to find a node containing a specific value.  

6. **Updating**  
   - Modify the data of an existing node.  

---

###  Advantages of Linked Lists
- **Dynamic Memory Allocation** – size can grow or shrink during runtime.  
- **Efficient Insertion/Deletion** – no shifting of elements is required (unlike arrays).  
- **Memory Utilization** – no pre-allocation of memory, avoids memory wastage.  
- Useful for implementing **advanced data structures** like stacks, queues, and graphs.  

---

###  Disadvantages of Linked Lists
- **Extra Memory Overhead** – each node requires additional space for storing pointers.  
- **Sequential Access Only** – no random access; traversal must start from the head.  
- **Slower Traversal** – compared to arrays due to pointer dereferencing.  
- **Complex Implementation** – especially for doubly and circular linked lists.

---

##  1.Singly Linked Note
This program demonstrates the **basic creation of a Node in a singly linked list** using C++.  

- A `Node` class is defined with two members:  
  - `val` → stores the data (integer).  
  - `next` → pointer to the next node (initialized as `NULL`).  
- A constructor initializes the `Node` object with a value.  
- In the `main()` function:  
  - A new node is dynamically created with value `20`.  
  - The program prints the node’s data (`val`) and its `next` pointer (which will be `NULL`).  

This serves as the **foundation for building a linked list** in C++.  

---

##  Algorithm  
1. **Start** the program.  
2. Define a **class `Node`** with:  
   - An integer variable `val`.  
   - A pointer `Node* next`.  
   - A constructor that assigns `val = data` and sets `next = NULL`.  
3. In the `main()` function:  
   - Create a new node dynamically with value `20` using `new Node(20)`.  
   - Print the `val` of the node.  
   - Print the `next` pointer (should display `0` or `NULL`).  
4. **End** the program.  

---

##  2.Insertion of node at the head 
This program demonstrates the **insertion of nodes at the head (beginning)** of a **singly linked list** in C++.  

- A class `Link` is created with:  
  - `data` → to store integer values.  
  - `next` → a pointer to the next node.  
  - A constructor that initializes the node with a value and sets `next = NULL`.  

- **Functions used:**  
  - `insert_head(Link* &head, int data)` → Inserts a new node at the beginning of the linked list.  
  - `disp(Link* head)` → Displays the linked list elements until the end (`NULL`).  

- **In `main()`**:  
  - A linked list is initially empty (`head = NULL`).  
  - Nodes with values `30`, `20`, and `10` are inserted at the head one by one.  
  - After each insertion, the list is displayed.  

---

##  Algorithm  

1. **Start** the program.  
2. Define a **class `Link`** with:  
   - An integer variable `data`.  
   - A pointer `Link* next`.  
   - A constructor to initialize `data` and set `next = NULL`.  
3. Define the function `insert_head(Link* &head, int data)`:  
   - Create a new node with the given `data`.  
   - Set `new_node->next = head`.  
   - Update `head = new_node`.  
4. Define the function `disp(Link* head)`:  
   - Initialize a temporary pointer `temp = head`.  
   - Traverse the list while `temp != NULL`.  
   - Print `temp->data` and move `temp = temp->next`.  
   - Print `NULL` at the end.  
5. In the `main()` function:  
   - Initialize `head = NULL`.  
   - Call `insert_head(head, 30)` and display the list.  
   - Call `insert_head(head, 20)` and display the list.  
   - Call `insert_head(head, 10)` and display the list.  
6. **End** the program.  

---

## 3. Adding more nodes  
This program demonstrates the **creation and traversal of a singly linked list** in C++.  
- A `Node` class is defined with:  
  - `val` → to store integer data.  
  - `next` → pointer to the next node.  
  - A constructor initializes a node with the given value and sets `next = NULL`.  

- In the `main()` function:  
  - Three nodes (`n1`, `n2`, `n3`) are dynamically created with values `10`, `20`, and `30`.  
  - The nodes are linked together:  
    - `n1 -> n2`  
    - `n2 -> n3`  
    - `n3 -> NULL`  
  - A pointer `temp` is used to traverse the list starting from the head (`n1`).  
  - Each node’s value is printed until the list ends (`NULL`).  

This demonstrates how nodes are linked together and how to traverse a linked list.  

---

##  Algorithm  

1. **Start** the program.  
2. Define a **class `Node`** with:  
   - An integer `val`.  
   - A pointer `Node* next`.  
   - A constructor to initialize `val = data` and `next = NULL`.  
3. In `main()` function:  
   - Create three nodes dynamically: `n1(10)`, `n2(20)`, `n3(30)`.  
   - Link the nodes:  
     - Set `n1->next = n2`.  
     - Set `n2->next = n3`.  
     - `n3->next` remains `NULL`.  
   - Initialize `temp = n1` (start traversal from head).  
   - While `temp != NULL`:  
     - Print `temp->val`.  
     - Move `temp = temp->next`.  
4. **End** the program.  

---


##  Conclusion
Linked lists in C++ are a **powerful and flexible data structure** that allow dynamic memory management and efficient insertion/deletion of elements. Unlike arrays, they do not require contiguous memory, making them well-suited for scenarios where the size of data cannot be predetermined.  
They serve as the foundation for implementing various advanced data structures such as **stacks, queues, deques, graphs, and adjacency lists**.  
However, linked lists also come with trade-offs, including **extra memory overhead** for pointers and the lack of direct random access.  

In summary:  
- Use **linked lists** when frequent insertions and deletions are required.  
- Use **arrays** when fast random access is needed.  
Choosing between arrays and linked lists depends on the **specific problem requirements** and the operations that need to be optimized.
