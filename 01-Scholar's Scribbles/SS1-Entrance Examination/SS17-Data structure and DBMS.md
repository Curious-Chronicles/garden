---
index: SS17
marks: 5
tags: entrance, data-structure, DBMS
related: [[]]
status: Completed
created: [[2023-05-06]]
---


## 1. Arrays

1. Definition:
An array is a data structure that stores a fixed-size sequence of elements of the same data type. It provides a way to store multiple values under a single variable name and allows accessing and manipulating individual elements using an index.

2. Declaration and Initialization:
Arrays are declared by specifying the data type of the elements they will hold, followed by the array name and the size of the array in square brackets. Initialization can be done at the time of declaration or later using assignment statements.

Example:
```
int numbers[5]; // Declaration of an integer array with size 5

int values[] = {1, 2, 3, 4, 5}; // Declaration and initialization of an integer array

float grades[3] = {98.5, 85.0, 92.3}; // Declaration and initialization of a float array
```

3. Indexing:
Array elements are accessed using zero-based indexing, where the first element is at index 0, the second element is at index 1, and so on. The index is specified inside square brackets after the array name.

Example:
```
int value = numbers[2]; // Accessing the element at index 2 of the 'numbers' array

grades[1] = 89.7; // Modifying the element at index 1 of the 'grades' array
```

4. Operations and Manipulation:
Arrays support various operations such as inserting, deleting, updating, and searching for elements. These operations can be performed using loops and conditional statements.

Example:
```
// Inserting an element at the end of the array
numbers[5] = 10;

// Deleting an element by shifting the remaining elements
for (int i = 2; i < 5; i++) {
    numbers[i] = numbers[i+1];
}

// Updating an element at a specific index
values[3] = 7;

// Searching for an element in the array
int index = -1;
for (int i = 0; i < 5; i++) {
    if (numbers[i] == 10) {
        index = i;
        break;
    }
}
```

Arrays are widely used in programming for storing and manipulating collections of data efficiently. They provide a convenient way to access and work with multiple elements using a single variable.

## 2. Stacks and Queues

1. Stack:
- Definition: A stack is a linear data structure that follows the Last-In-First-Out (LIFO) principle. It allows inserting and removing elements from only one end, called the top of the stack.
- Operations:
  - Push: Adds an element to the top of the stack.
  - Pop: Removes the top element from the stack.
  - Peek: Returns the value of the top element without removing it.
- Example: A stack can be visualized as a stack of plates, where the last plate added is the first one to be removed.

2. Queue:
- Definition: A queue is a linear data structure that follows the First-In-First-Out (FIFO) principle. It allows inserting elements at one end, called the rear, and removing elements from the other end, called the front.
- Operations:
  - Enqueue: Adds an element to the rear of the queue.
  - Dequeue: Removes the element from the front of the queue.
  - Peek: Returns the value of the front element without removing it.
- Example: A queue can be visualized as people standing in a line, where the person who arrived first is the first one to be served.

3. Application:
- Stacks: Stacks are used in applications that require a last-in-first-out behavior, such as function calls, expression evaluation, and backtracking algorithms.
- Queues: Queues are used in applications that require a first-in-first-out behavior, such as job scheduling, breadth-first search, and message passing.

4. Implementation:
- Stack: Stacks can be implemented using arrays or linked lists.
- Queue: Queues can be implemented using arrays, linked lists, or circular arrays.

5. Complexity:
- The time complexity for the main operations of stacks and queues is O(1) since elements are added or removed from the top (stack) or front (queue) in constant time.

Understanding stacks and queues is essential for mastering various data structures and algorithms. They provide efficient ways to manage and process data based on specific access patterns, making them valuable tools in computer science and software development.

## 3. Linked Lists

1. Singly Linked List:
- Definition: A singly linked list is a linear data structure in which each element, called a node, contains a data field and a reference (or link) to the next node in the list. The last node points to NULL, indicating the end of the list.
- Operations:
  - Insertion: Adds a new node at the beginning, end, or a specific position in the linked list.
  - Deletion: Removes a node from the linked list, adjusting the references of the surrounding nodes.
  - Traversal: Visits each node in the linked list to access or modify its data.
- Example: A singly linked list can be visualized as a chain of nodes, where each node contains data and a pointer to the next node.

2. Doubly Linked List:
- Definition: A doubly linked list is a variation of the linked list in which each node has references to both the next and previous nodes. This allows traversal in both forward and backward directions.
- Operations:
  - Insertion: Adds a new node at the beginning, end, or a specific position in the linked list.
  - Deletion: Removes a node from the linked list, adjusting the references of the surrounding nodes.
  - Traversal: Visits each node in the linked list to access or modify its data, in both forward and backward directions.
- Example: A doubly linked list can be visualized as a chain of nodes with two pointers, one for the next node and another for the previous node.

3. Circular Linked List:
- Definition: A circular linked list is a variation of the linked list in which the last node points back to the first node, forming a circular structure. This allows seamless traversal from the last node to the first node.
- Operations:
  - Insertion: Adds a new node at the beginning, end, or a specific position in the linked list.
  - Deletion: Removes a node from the linked list, adjusting the references of the surrounding nodes.
  - Traversal: Visits each node in the linked list to access or modify its data.
- Example: A circular linked list can be visualized as a looped chain of nodes, where the last node points back to the first node.

4. Complexity:
- The time complexity for insertion and deletion in linked lists is O(1) since it only involves modifying the links of a few nodes.
- The traversal operation has a time complexity of O(n) since it visits each node in the linked list.

Linked lists are fundamental data structures that provide dynamic memory allocation and efficient insertion and deletion operations. They are widely used in various applications, such as implementing stacks, queues, and hash tables, and are essential to understand when studying data structures and algorithms.

## 4. Trees

1. Binary Tree:
- Definition: A binary tree is a hierarchical data structure in which each node has at most two children, referred to as the left child and the right child. The left child is smaller than the parent, and the right child is greater or equal to the parent, based on some defined order.
- Operations:
  - Insertion: Adds a new node to the binary tree, following the order property.
  - Traversal: Visits each node in the binary tree in a specific order, such as in-order, pre-order, or post-order traversal.
- Example: A binary tree can be visualized as a collection of nodes, where each node has at most two child nodes.

2. Binary Search Tree (BST):
- Definition: A binary search tree is a variant of the binary tree in which the left child is smaller than the parent, and the right child is greater or equal to the parent. It allows efficient searching, insertion, and deletion operations.
- Operations:
  - Insertion: Adds a new node to the binary search tree while maintaining the order property.
  - Search: Looks for a specific value in the binary search tree.
  - Deletion: Removes a node from the binary search tree, adjusting the structure to maintain the order property.
- Example: A binary search tree can be visualized as a binary tree with the order property, where the left subtree of a node contains values smaller than the node, and the right subtree contains values greater than or equal to the node.

3. Balanced Trees:
- Definition: Balanced trees are binary trees in which the heights of the left and right subtrees of any node differ by at most one. They aim to maintain the tree's balance to ensure efficient operations.
- Examples: Some examples of balanced trees include AVL trees, Red-Black trees, and B-trees.

4. Tree Traversal:
- Pre-order Traversal: Visits the root node first, then recursively visits the left subtree and the right subtree.
- In-order Traversal: Recursively visits the left subtree, then the root node, and finally the right subtree. In a binary search tree, this traversal visits nodes in ascending order.
- Post-order Traversal: Recursively visits the left subtree, then the right subtree, and finally the root node.
- Level-order Traversal: Visits the nodes level by level, from left to right.

Trees are versatile data structures used in various applications, such as file systems, hierarchical databases, and decision-making algorithms. Understanding the different types of trees and their traversal methods is essential for efficient data storage and retrieval.

## 5. Graphs

1. Graph Representation:
- Definition: A graph is a non-linear data structure consisting of a set of vertices (nodes) connected by edges. It is used to represent relationships between objects.
- Types of Graphs:
  - Directed Graph (Digraph): Each edge has a specific direction, indicating a one-way relationship between vertices.
  - Undirected Graph: Edges do not have a specific direction, indicating a two-way relationship between vertices.
- Graph representation methods include adjacency matrix and adjacency list.

2. Graph Traversal:
- Depth-First Search (DFS): Explores as far as possible along each branch before backtracking. It uses a stack or recursion to traverse the graph.
- Breadth-First Search (BFS): Explores all the vertices of a graph in breadth-first order, visiting vertices at the same level before moving to the next level. It uses a queue to traverse the graph.

3. Graph Algorithms:
- Shortest Path: Finding the shortest path between two vertices in a graph, often using algorithms like Dijkstra's algorithm or Bellman-Ford algorithm.
- Minimum Spanning Tree: Finding a tree that connects all vertices of a graph with the minimum total edge weight, commonly using algorithms like Prim's algorithm or Kruskal's algorithm.
- Topological Sorting: Ordering the vertices of a directed acyclic graph (DAG) in a linear order such that for every directed edge (u, v), vertex u comes before vertex v in the order.

4. Graph Connectivity:
- Connected Graph: A graph where there is a path between every pair of vertices.
- Strongly Connected Graph: A directed graph where there is a directed path between every pair of vertices.
- Weakly Connected Graph: A directed graph that becomes connected when all its directed edges are treated as undirected edges.

Graphs are widely used in various domains, such as social networks, routing algorithms, recommendation systems, and network analysis. Understanding the properties, traversal techniques, and algorithms related to graphs is crucial for analyzing and solving problems that involve complex relationships between entities.

## 6. Hash Tables

1. Hash Table Definition:
- A hash table is a data structure that stores key-value pairs, where the keys are unique and are used to access the corresponding values. It provides efficient insertion, deletion, and retrieval operations.

2. Hash Function:
- A hash function is a function that takes a key as input and computes a hash value or hash code. It maps the key to an index or bucket in the hash table.
- The hash function should be deterministic, meaning that the same key should always produce the same hash value.
- A good hash function aims to distribute the keys uniformly across the hash table, reducing the number of collisions.

3. Collision Handling:
- Collision occurs when two or more keys produce the same hash value and need to be stored in the same bucket of the hash table.
- Collision handling techniques include:
  - Separate Chaining: Each bucket of the hash table contains a linked list to store multiple values with the same hash value.
  - Open Addressing: The hash table itself is used to store all the key-value pairs, and in case of collision, a new location is searched within the table.
    - Linear Probing: If a collision occurs, the next available bucket is checked linearly until an empty slot is found.
    - Quadratic Probing: If a collision occurs, the algorithm uses a quadratic function to probe for the next available bucket.
    - Double Hashing: If a collision occurs, a secondary hash function is used to calculate the step size for probing.

4. Hash Table Operations:
- Insertion: The key-value pair is hashed to determine the bucket and is stored in that bucket.
- Lookup/Retrieval: The key is hashed to find the corresponding bucket, and the value associated with the key is retrieved.
- Deletion: The key is hashed to find the bucket, and the corresponding key-value pair is removed from the hash table.

Hash tables are commonly used in various applications such as dictionaries, symbol tables, caches, and databases. They offer fast access and retrieval times, making them efficient for storing and retrieving data based on unique keys.

## 7. Sorting Algorithms

1. Bubble Sort:
- Bubble Sort is a simple sorting algorithm that repeatedly compares adjacent elements and swaps them if they are in the wrong order.
- It iterates through the list multiple times, pushing the largest unsorted element to its correct position in each iteration.
- Example: [5, 2, 8, 12, 3]
  - Pass 1: [2, 5, 8, 3, 12]
  - Pass 2: [2, 5, 3, 8, 12]
  - Pass 3: [2, 3, 5, 8, 12]

2. Selection Sort:
- Selection Sort divides the list into a sorted and an unsorted part. It repeatedly selects the smallest element from the unsorted part and swaps it with the element at the beginning of the unsorted part.
- Example: [7, 2, 4, 1, 5]
  - Pass 1: [1, 2, 4, 7, 5]
  - Pass 2: [1, 2, 4, 7, 5]
  - Pass 3: [1, 2, 4, 7, 5]
  - Pass 4: [1, 2, 4, 5, 7]

3. Insertion Sort:
- Insertion Sort builds the final sorted list one item at a time by shifting larger elements to the right.
- It starts with the second element and compares it with the previous elements, inserting it at the correct position in the sorted part.
- Example: [3, 8, 2, 5, 1]
  - Pass 1: [3, 8, 2, 5, 1]
  - Pass 2: [2, 3, 8, 5, 1]
  - Pass 3: [2, 3, 5, 8, 1]
  - Pass 4: [1, 2, 3, 5, 8]

4. Merge Sort:
- Merge Sort is a divide-and-conquer algorithm that divides the list into two halves, recursively sorts them, and then merges the sorted halves.
- It repeatedly compares the elements from the two halves and merges them in the correct order.
- Example: [6, 2, 9, 1, 7]
  - Split: [6, 2, 9], [1, 7]
  - Split: [6], [2, 9], [1], [7]
  - Merge: [2, 6, 9], [1, 7]
  - Merge: [1, 2, 6, 7, 9]

5. Quick Sort:
- Quick Sort is a divide-and-conquer algorithm that selects a pivot element and partitions the list into two sub lists, one with elements less than the pivot and one with elements greater than the pivot.
- It then recursively sorts the sub lists. The pivot is placed in its final position after each partition.
- Example: [4, 7, 2, 1, 9]
  - Pivot: 4
  - Partition: [2, 1], [4], [7, 9]
  - Pivot: 2
  - Partition: [1], [2], [7, 9]
  - Pivot: 7
  - Partition: [1], [2], [7], [9]

Sorting algorithms are used to arrange elements in a specific order, such as ascending or descending, to facilitate searching and

## 8. Searching Algorithms

1. Linear Search:
- Linear Search is a simple searching algorithm that sequentially checks each element in a list until a match is found or the end of the list is reached.
- It starts from the beginning and compares each element with the target value.
- Example: Searching for value 7 in [3, 6, 2, 7, 9]
  - Iteration 1: 3 (not a match)
  - Iteration 2: 6 (not a match)
  - Iteration 3: 2 (not a match)
  - Iteration 4: 7 (found at index 3)

2. Binary Search:
- Binary Search is a more efficient searching algorithm for sorted lists. It repeatedly divides the search space in half by comparing the target value with the middle element.
- If the middle element is a match, the search is successful. Otherwise, it eliminates half of the remaining search space and continues the process.
- Example: Searching for value 5 in [1, 2, 3, 4, 5, 6, 7, 8, 9]
  - Iteration 1: Compare with middle element 5 (found)
  
3. Interpolation Search:
- Interpolation Search is an improved version of binary search that works best on uniformly distributed sorted lists.
- It estimates the position of the target value based on the values of the first and last elements.
- Example: Searching for value 6 in [2, 4, 6, 8, 10]
  - Estimated position: (6 - 2) / (10 - 2) * (4 - 2) = 2
  - Iteration 1: Compare with element at index 2 (found)

4. Hashing:
- Hashing is a searching technique that uses a hash function to map keys to array indices, allowing for direct access to elements.
- It is efficient for large data sets and provides constant-time average search complexity.
- Example: Searching for key "John" in a hash table
  - Hash function generates index 3
  - Element at index 3 is "John" (found)
  
5. Jump Search:
- Jump Search is a searching algorithm that works on sorted lists. It jumps ahead by a fixed step size and then performs linear search in the block where the target value is expected to be.
- It reduces the number of comparisons compared to linear search.
- Example: Searching for value 5 in [1, 3, 5, 7, 9]
  - Step size: √5 = 2
  - Block 1: Compare with element 3 (not a match)
  - Block 2: Compare with element 5 (found)

Searching algorithms are used to find the presence or location of a target value in a given collection of data. They are essential tools in data analysis and retrieval operations.

## 9. Relational Database Management System

1. Relational Database:
- A relational database is a structured collection of data organized into tables with predefined relationships between them.
- It follows the relational model, where data is stored in tables consisting of rows (records) and columns (attributes).
- Examples: MySQL, Oracle Database, Microsoft SQL Server.

2. Tables:
- Tables are the fundamental structure in a relational database and represent entities or concepts.
- Each table has a name and consists of rows and columns.
- Rows contain individual records, and columns represent attributes or properties of the records.
- Example: A "Customers" table with columns like "CustomerID," "Name," "Email," and "Address."

3. Relationships:
- Relationships define the connections between tables in a relational database.
- The two main types of relationships are:
  - One-to-One (1:1): Each record in one table is associated with exactly one record in another table.
  - One-to-Many (1:N): Each record in one table can be associated with multiple records in another table.
- Examples: A "Customers" table can have a one-to-many relationship with an "Orders" table.

4. Primary Key:
- A primary key is a unique identifier for each record in a table.
- It ensures that each record can be uniquely identified and serves as a reference point for relationships.
- Example: In a "Customers" table, the "CustomerID" column can be designated as the primary key.

5. Foreign Key:
- A foreign key is a field in one table that refers to the primary key of another table.
- It establishes relationships between tables by matching the values of the foreign key with the corresponding primary key.
- Example: In an "Orders" table, the "CustomerID" column can be a foreign key referencing the "CustomerID" column in the "Customers" table.

6. SQL (Structured Query Language):
- SQL is a programming language used to communicate with and manipulate relational databases.
- It provides commands for creating, querying, updating, and managing the database.
- Example: SELECT * FROM Customers WHERE Country='USA';

Relational Database Management Systems (RDBMS) are widely used for storing and managing structured data. They provide powerful tools for data organization, retrieval, and maintaining relationships between entities.

## 10. SQL Commands and Queries

1. SELECT:
- The SELECT command is used to retrieve data from a database table.
- It allows you to specify the columns you want to retrieve and the table(s) you want to retrieve data from.
- Example: SELECT column1, column2 FROM table_name;

2. INSERT:
- The INSERT command is used to insert new records into a database table.
- It requires specifying the table name and the values to be inserted.
- Example: INSERT INTO table_name (column1, column2) VALUES (value1, value2);

3. UPDATE:
- The UPDATE command is used to modify existing records in a database table.
- It allows you to specify the table name, the columns to be updated, and the new values.
- Example: UPDATE table_name SET column1 = value1 WHERE condition;

4. DELETE:
- The DELETE command is used to delete records from a database table.
- It allows you to specify the table name and the condition for selecting the records to be deleted.
- Example: DELETE FROM table_name WHERE condition;

5. WHERE:
- The WHERE clause is used to filter records in a SQL query.
- It allows you to specify a condition that must be satisfied for the records to be selected.
- Example: SELECT column1, column2 FROM table_name WHERE condition;

6. JOIN:
- The JOIN operation is used to combine rows from two or more tables based on related columns.
- It allows you to specify the type of join (e.g., INNER JOIN, LEFT JOIN) and the columns to join on.
- Example: SELECT table1.column1, table2.column2 FROM table1 JOIN table2 ON table1.column = table2.column;

7. GROUP BY:
- The GROUP BY clause is used to group rows based on one or more columns.
- It is often used with aggregate functions (e.g., SUM, COUNT) to perform calculations on grouped data.
- Example: SELECT column1, SUM(column2) FROM table_name GROUP BY column1;

8. ORDER BY:
- The ORDER BY clause is used to sort the result set in ascending or descending order.
- It allows you to specify the columns to sort by.
- Example: SELECT column1, column2 FROM table_name ORDER BY column1 ASC;

These SQL commands and queries are fundamental for interacting with relational databases and manipulating data. They provide a powerful set of tools for retrieving, inserting, updating, and deleting records, as well as performing operations like joining tables, grouping data, and sorting results.
