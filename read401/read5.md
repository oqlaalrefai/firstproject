## Big O: Analysis of Algorithm Efficiency
Big O(oh) notation is used to describe the efficiency of an algorithm or function. 
efficiency is evaluated based on 2 factors:
  - Running Time
  - Memory Space
- Big O’s role in algorithm efficiency is to describe the Worst Case of efficiency an algorithm can have in performing it’s job

- **Input Size**
Input Size refers to the size of the parameter values that are read by the algorithm.
higher input size will increase to Running Time and Memory Space.

### **Units of Measurement**
1- in order to quantify the Running Time in our analysis, we will consider Three Measurements of time:
  - The time in milliseconds from the start of a function execution until it ends
  - The number of operations that are executed
  - The number of “Basic Operations” that are executed
2- In order to quantify Memory Space, we can consider Four Sources of Memory Usage during function run-time:
  - The amount of space needed to hold the code for the algorithm
  - The amount of space needed to hold the input data.
  - The amount of space needed for the output data.
  - The amount of space needed to hold working space during the calculation

### Orders of Growth
We can describe overall efficiency by using the input size n and measuring the overall Units of Space the Order of Growth represents the increase in Running Time or Memory Space.
**Constant Complexity** means that no matter what inputs are thrown at our algorithm, it always uses the same amount of time or space
**Logarithmic Complexity** represents a function that sees a decrease in the rate of complexity growth, the greater our value of n.
- If an algorithm has Linear Complexity, the size of our inputs ‘n’ will directly determine the amount of Memory Space used and Running Time length. 
**Linearithmic Complexity** is used to describe a growth rate of n by lgn
**Quadratic Complexity** describes an algorithm with complexity growing at a rate of input size n multiplied by n
**Cubic Complexity** is typically just a higher degree of what makes the quadratic complexity grow at such a high rate.
**Exponential Complexity** represents very rapidly growing complexity, such that whatever our input size n

- Worst Case: The efficiency for the worst possible input of size n .
- Best Case: The efficiency for the best possible input of size n .
- Average Case: The efficiency for a “typical” or “random” input of size n.

### Asymptotic Notations
  - Big O(oh): This notation describes the Worst Case for an algorithm. The Order of Growth used represents the upper bounds of Time and Space.
  - Big Omega: This notation describes the Best Case for a given algorithm. The Order of Growth used represents the lower bounds of Time and Space.
  - Big Theta: This notation describes the Average Case. The Order of Growth used represents the tight bound of Time and Space.

## Linked List 
is a sequence of Nodes that are connected/linked to each other. The most defining feature of a Linked List is that each Node references the next Node in the link.

![linked list](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2013/03/Linkedlist.png)

- here are two types of Linked List :
  - **Singly** :Singly refers to the number of references the node has. A Singly linked list means that there is only one reference, and the reference points to the Next node in a linked list. 
  - **Doubly** :Doubly refers to there being two (double) references within the node. A Doubly linked list means that there is a reference to both the Next and Previous node.
     - there are two references contained within each node: a reference to the next node, as well as the previous node
- **Node** are the individual items/links that live in a linked list. Each node contains the data for each link.
- **Head** is a reference of type Node to the first node in a linked list.
  - The starting point of the list is a reference to the first node, which is referred to as the head
- **Current** is a reference of type Node to the node that is currently being looked a
- you are not able to use a foreach or for loop. We depend on the Next value in each node to guide us where the next reference is pointing. 
- The end of the list isn’t a node, but rather a node that points to null, or an empty value.
#### **linear data structures** 
there is a sequence and an order to how they are constructed and traversed.
we have to go through all of the items in the list in order, or sequentially.

#### **non-linear data structures** 
items don’t have to be arranged in order, which means that we could traverse the data structure non-sequentially.

## Memory management
The biggest differentiator between arrays and linked lists is the way that they use memory in our machines.
- When an array is created, it needs a certain amount of memory we’d need all of that memory in one contiguous block.
  - array is static data structures
- when a linked list is born, it doesn’t need all bytes of memory all in one place.
  - linked list is dynamic data structures
![memorization](https://miro.medium.com/max/875/1*G43FVT5xJ1n1QDKVNZUxXQ.jpeg)  

### **A circular linked list **
is a little odd in that it doesn’t end with a node pointing to a null value. Instead, it has a node that acts as the tail of the list (rather than the conventional head node), and the node after the tail node is the beginning of the list. 

## when the linkedList is the best choice and when it the worst choice
![array vs linkedLis](https://miro.medium.com/max/875/1*cUehR5S18XSoVLaPNfNzlA.jpeg)












