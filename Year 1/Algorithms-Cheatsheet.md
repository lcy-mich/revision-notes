# [1] Notes
made lovingly by me for you <3

## ADT vs Datastructures

ADTs (**WHAT**) classify data-3structures based on behaviour (what the user sees)

Datastructures (**HOW**) are the actual implementation/ concrete representation of data (what the implementer sees)

|      ADT       |          DATASTRUCTURE        |
| -------------- | ----------------------------- |
|      ARRAY     |             array             |
|      LIST      |       array/ linkedlist       |
|      QUEUE     |       array/ linkedlist       |
|      STACK     |       array/ linkedlist       |
|    SET/ BAG    |            hashtable          |
|       MAP      | array/ hashtable/ linkedlist  |
| PRIORITY QUEUE |          array/ heap          |

---

## Array
- used to store **homogenous items in contiguous memory**
- they are linear data structures

- memory address m of array element i with size s at array with base-address b: _m = b + (i*s)_

- array **has** to be resized when full
- arrays should always be between 25% and 100% full
- grow array
	- if array is full, create new array twice the size and copy items over
- shrink array
	- if array is one-quarter full, halve the size
	  
## Circular Array
- tail and head pointers loop-over with modular arithmetic
- used in queues

---

## (Singly) Linked List
- used to maintain a **dynamic collection of heterogenous items**

- nodes contain data item and reference to next node

- head pointer points to first node
- tail pointer points to last node (with next pointer null)

## Doubly Linked List
- nodes contain data item, reference to previous node **and** reference to next node

- head pointer's previous pointer is null
- tail pointer's next pointer is null

## Binary Heap
A complete binary tree where:
- keys are stored in nodes
- parent's keys are >= / <= children's keys (heap order)
	- root has the max/ min key
 
## Binary Tree
a non-linear ADT thats either
- empty
- a tree consisting of one node called the root, and zero to two disjoint (sub)trees called children

## Strongly-connected Components

### Kosaraju-Sharir Algorithm
- Find topological order in G reversed
- Run DFS in G, visiting unmarked vertices in reverse post-order of G reversed


# [2] ADTs

## Array

fixed-size collection of elements accessible by an index

### API

- set(index, element)
- get(index)

### Complexity Analysis
Datastructures used to implement:
- Array
---
#### > Regular Array Datastructure

| Operation | Complexity |
| --------- | ---------- |
|    get    |    O(1)    |
|    set    |    O(1)    |

--------------------------------------------------------------------------------------
## List

stores sequential elements

### API

- append(item)
- prepend(item)
- head()
    - first item
- tail()
    - all items other than first item

### Complexity Analysis
Datastructures used to implement:
- Array
- Linked List


--------------------------------------------------------------------------------------
## Stack

a list that restricts where you can add/remove elements (LIFO)

two pointers, bottom and top

### API

- push(item)
    - increments top pointer and sets value to item
- pop()
    - returns value at top and decrements top
- isEmpty()

### Complexity Analysis
Datastructures used to implement:
- Array
- Linked List
---
#### > Array  
worst time complexity is due to array resizing
| Operation | Best | Worst | Amortized |
| --------- | ---- | ----- | --------- |
|    push   | O(1) | O(N)  |    O(1)   |
|    pop    | O(1) | O(N)  |    O(1)   |

#### > Linked List
| Operation | Complexity |
| --------- | ---------- |
|    push   |    O(1)    | 
|    pop    |    O(1)    |

--------------------------------------------------------------------------------------
## Queue

a list that restricts where you can add/remove elements (FIFO)

two pointers, tail and head

### API

- enqueue(item)
    - decrements tail and sets item at tail
- dequeue()
    - returns value at head and decrements head

### Complexity Analysis
Datastructures used to implement:
- Array/ Circular Array
- Linked List
---
#### > Array

| Operation | Complexity |
| --------- | ---------- |
|  enqueue  |    O(1)    |
|  dequeue  |    O(1)    |

---
#### > Circular Array

| Operation | Complexity |
| --------- | ---------- |
|  enqueue  |    O(1)    |
|  dequeue  |    O(1)    |

---
#### > Linked List
| Operation | Complexity |
| --------- | ---------- |
|  enqueue  |    O(1)    | 
|  dequeue  |    O(1)    |


--------------------------------------------------------------------------------------
## Set & Multiset / Bag

a set stores unindexed, unordered, unrepeated elements

a bag/ multiset also stores unindexed, unordered elements but can be repeated

### API

- insert(item)
- remove(item)
- contains(item)

--------------------------------------------------------------------------------------
## Binary Search Tree

a binary tree in symmetric order

symmetric order means
- for every node, its key is larger than all keys in left subtree
- for every node, its key is smaller than all keys in right subtree

### API

- get(key) / search(key)
- put(key, value) / insert(key, value)

### Complexity Analysis
Datastructures used to implement:
- Binary Tree

---
#### > Binary Tree
| Operation |       Cost      |
| --------- | --------------- |
|    get    | 1 + tree depth  | 
|    put    | 1 + tree depth  | 

**average get and put are also both sqrt N if deletions are allowed**

| Operation | Average | Worst |
| --------- | ------- | ----- |
|    get    | c log N |   N   |
|    put    | c log N |   N   |
|   delete  | sqrt N  |   N   |

--------------------------------------------------------------------------------------
## 2-3 Search Tree

a tree where each node is either:
- 2-node: one key, two children
- 3-node: two keys, three children

perfect balance, symmetric order

### API

- get(key) / search(key)
- put(key, value) / insert(key, value)

### Complexity Analysis
Guaranteed logarithmic performance (c log N)

Tree height
- Worst case: log N (all nodes are 2-nodes)
- Best case: log_3 N (all nodes are 3-nodes)
  
--------------------------------------------------------------------------------------
## Left-leaning Red-Black Tree

a BST such that:
- every path from root to null links has same number of black links (perfect black balance)
- no node has 2 red links connected to it (that would represent 4-node)
- red links lean left

there exists 1-1 correspondence between a 2-3 tree and LLRB tree

### API

- get(key) / search(key)
- put(key, value) / insert(key, value)

### Complexity Analysis
Guaranteed logarithmic performance (c log N)

Tree height
- Worst case: 2 log N
  
--------------------------------------------------------------------------------------
## Map/ Dictionary/ Associative Array/ Symbol Table

a list that can hold data in key-value pairs

keys are unique and can only hold one value

keys have a total order relation
- antisymmetry (if a <= b and b <= a then a = b)
- transitivity (if a <= b and b <= c then a <= c)
- totality (a <= b or b <= a)

### API

- insert(key, value) / put(key, value)
- remove(key)
- update(key, value)
- lookup(key) / get(key)

EXTENDED API

- min/max
- ordered iteration
- floor/ceiling
- rank
- select

### Complexity Analysis
Datastructures used to implement:
- Array
- Linked List
- Binary Tree
- Hashtable
  
| Datastructure |   Average  |
| ------------- | ---------- |
|     Array     |    O(N)    |
|   Hashtable   |    O(1)    |

- **BST average search and average insert are also both square root of N if deletions are allowed**
- **SC/ separate chaining and LP/ linear probing analysis is under uniform hashing assumptions**

| Datastructure  |   Worst Search  |   Avg Search  |   Worst Insert  |   Avg Insert  | Worst Del | Avg Del |
| -------------- | --------------- | ------------- | --------------- | ------------- | --------- | ------- |
| Unordered List |        N        |      N/2      |         N       |       N       |     N     |   N/2   |
|  Ordered Array |      log N      |     log N     |         N       |      N/2      |     N     |   N/2   |
|       BST      |        N        |    c log N    |         N       |    c log N    |     N     | sqrt N  |
|    2-3 Tree    |     c log N     |    c log N    |     c log N     |    c log N    |  c log N  | c log N |
|   LLRB Tree    |     2 log N     |    2 log N    |     2 log N     |    1 log N    |  1 log N  | 1 log N |
|  SC Hashtable  |      log N      |     log N     |      log N      |     3 - 5     |   3 - 5   |  3 - 5  |
|  LP Hashtable  |        N        |       N       |        N        |     3 - 5     |   3 - 5   |  3 - 5  |

---
#### > Linked List (sequential search)
|     Operation     |     Cost   |
| ----------------- | ---------- |
|        get        |      N     | 
|        put        |      N     |
|      min/max      |      N     |
| ordered iteration |  N log N   |
|   floor/ceiling   |      N     |
|       rank        |      N     |
|      select       |      N     |
|      delete       |      N     |

---
#### > Ordered Array (binary search)
|     Operation     |     Cost   |
| ----------------- | ---------- |
|        get        |   log N    | 
|        put        |      N     |
|      min/max      |      1     |
| ordered iteration |      N     |
|   floor/ceiling   |    log N   |
|       rank        |    log N   |
|      select       |      1     |
|      delete       |      N     |

---
#### > Binary Search Tree
|     Operation     |     Cost   |
| ----------------- | ---------- |
|        get        | h ~ log N  | 
|        put        | h ~ log N  | 
|      min/max      | h ~ log N  | 
| ordered iteration |      N     |
|   floor/ceiling   | h ~ log N  | 
|       rank        | h ~ log N  | 
|      select       | h ~ log N  | 
|      delete       |            |

--------------------------------------------------------------------------------------
## Priority Queue

a queue where items are inserted/removed based on a priority

two pointers, head and tail

### API

- enqueue(item, priority)
- dequeue()

### Complexity Analysis
Datastructures used to implement:
- Array
- Heap

| Datastructure |   Average  |
| ------------- | ---------- |
|     Array     |    O(N)    |
|     Heap      |  O(log N)  |

---
#### > Unordered Array

| Operation | Complexity |
| --------- | ---------- |
|  enqueue  |    O(1)    |
|  dequeue  |    O(N)    |




# [3] Algorithms

## > Union-Find Problem
given graph with N nodes:
- union(nodeA, nodeB)
	- connects two nodes
- find(nodeA, nodeB)
	- is nodeA and nodeB connected?

### Quick-find
#### Freq of accesses
| init | union | find |
| ---- | ----- | ---- |
|  N   |   N   |  1   |

N unions on N objects = ~N^2

### Quick-union
#### **Worst case** freq of accesses
| init | union | find |
| ---- | ----- | ---- |
|  N   |   N   |  N   |

### Weighted Quick-union
| init | union | find  |
| ---- | ----- | ----- |
|  N   | log N | log N |

----------------------------------------------------------------------------------------------------------------
### > Find largest M items in stream of N items
### Array & Sort
| Time complexity | Space Complexity |
| --------------- | ---------------- |
| 	  N log N     |         N        |
### Elementary Priority Queue
| Time complexity | Space Complexity |
| --------------- | ---------------- |
| 	   M * N      |         M        |

### Binary Heap
#### Freq of compares
insertion: at most (1 + log N)
deletion: at most (2 log N)

#### Complexity
| Time complexity | Space Complexity |
| --------------- | ---------------- |
| 	  N log M     |         M        |

| Datastructure | Insert | Delete-max/min | find max/min |
| ------------- | ------ | -------------- | ------------ |
| Unordered Arr |   1    |       M        |      M       |
| Ordered Arr   |   M    |       1        |      1       |  
| Binary Heap   | log M  |     log M      |      1       |

----------------------------------------------------------------------------------------------------------------
## > Sorting
### Selection Sort
Inplace, Unstable

#### Freq of compares
(N-1) + (N-2) + ... + 1 + 0 = N^2 / 2
#### Freq of exchanges
= N
#### Complexity
Big Omega (N^2) = Big Theta (N^2) = Big O (N^2)

| worst | average | best  |
| ----- | ------- | ----- |
| ~N^2  |  ~N^2   | ~N^2  |

---
### Insertion Sort
Inplace, Stable

#### Freq of compares
on average ~ 1/4 N^2
#### Freq of exchanges
on average ~ 1/4 N^2

#### Complexity
Best case (already sorted array): N-1 compares, 0 exchanges
Big Omega (N)

Big Theta(N^2)

Worst Case (array in reverse order): ~1/2 N^2 compares, ~1/2 N^2 exchanges
Big O (N^2)

| worst | average | best  |
| ----- | ------- | ----- |
| ~N^2  |  ~N^2   |  ~N   |


---
### Merge Sort
Not inplace, Stable

#### Freq of compares
at most N log N
#### Freq of accesses
at most 6N log N

#### Complexity
Optimal as cost is proven limit for all **comparison-based** sorting
Cost ~N log N 
| Time complexity | Space Complexity |
| --------------- | ---------------- |
| 	  N log N     |        N         |

|  worst   | average  |   best   |
| -------- | -------- | -------- |
| ~N log N | ~N log N | ~N log N |


---
### Quick Sort
Inplace, Unstable

#### Freq of compares
on average ~ N log N
at most N + (N - 1) + (N - 2) + ... + 1 ~ 1/2 N^2

#### Complexity
| Time complexity | Space Complexity |
| --------------- | ---------------- |
| 	  N log N     |       log N      |

|  worst | average  |   best   |
| ------ | -------- | -------- |
|  ~N^2  | ~N log N | ~N log N |

---
### Heapsort
Inplace, Unstable

poor use of cache

#### Freq of compares
Heap construction: O(N)
Heapsort: O(N log N)
#### Freq of exchanges
O(N)
Heapsort: O(N log N)

#### Complexity
|  worst   | average  |   best   |
| -------- | -------- | -------- |
| ~N log N | ~N log N | ~N log N |

----------------------------------------------------------------------------------------------------------------
## > Undirected Graph Realisations

### Adjacency List
| Iterate over adjacent vertices | Edge(v, w) | Add Edge | Space Complexity |
| ------------------------------ | ---------- | -------- | ---------------- |
|           degree(v)            |  degree(v) |    1     |      V + E       |

---
### Adjacency Matrix

| Iterate over adjacent vertices | Edge(v, w) | Add Edge | Space Complexity |
| ------------------------------ | ---------- | -------- | ---------------- |
|               V                |     1      |    1     |       V^2        |

----------------------------------------------------------------------------------------------------------------
## > Find all vertices b connected to a vertex s

### Depth-first search
Time is proportional to sum of degrees
| Time complexity |
| --------------- |
|      E + V      |

---
### Breadth-first search

| Time complexity |
| --------------- |
|      E + V      |

---
### Connected Components
preprocess graph G via DFS to get v connected to w in **constant time**
- is v connected to w? -> cc[v] == cc[w]
- 
| Preprocess time |
| --------------- |
|  sum of degrees |

----------------------------------------------------------------------------------------------------------------
## > Directed Graph Realisations

### Adjacency List
| Iterate over adjacent vertices |  Edge(v, w)  | Add Edge | Space Complexity |
| ------------------------------ | ------------ | -------- | ---------------- |
|         outdegree(v)           | outdegree(v) |    1     |      V + E       |

---
### Adjacency Matrix

| Iterate over adjacent vertices | Edge(v, w) | Add Edge | Space Complexity |
| ------------------------------ | ---------- | -------- | ---------------- |
|               V                |     1      |    1     |       V^2        |

----------------------------------------------------------------------------------------------------------------
## > Minimum Spanning Tree

---
### Greedy Algorithm
given any cut, the crossing edge of min-weight is in the MST

---
### Kruskal's Algorithm
- consider edges in ascending order of weight
- add next edge to MST, unless it creates a cycle
- stop when all edges are considered (or when V-1 edges are added)

#### Complexity

#### Option 1:
- Check cycles with DFS(v) for if w is reachable
- cost: O(V) as tree contains at most V-1 edges

#### Option 2:
- use union-find datastructure and weighted quick-union realisation to check connectivity
- cost: O(log V)

worst case time complexity : E log E

|   Operation   | Frequency | Cost per operation |
| ------------- | --------- | ------------------ |
| Build the PQ  |     1     |       E log E      |
|  Delete min   |     E     |        log E       |
|     Union     |     V     |        log V       |
|     Find      |     E     |        log V       |

---
### Prim's Algorithm
- start at a vertex and greedy grow tree
- add T to min-weighted edge with exactly one endpoint in T
- stop when V-1 edges are added

#### Complexity

#### Option 1:
- try all edges
- cost: O(E)
#### Option 2:
- use priority queue containing all edges with at least one endpoint in T
- cost: O(log E)

|   Operation   | Frequency | Cost per operation |
| ------------- | --------- | ------------------ |
|  Delete min   |     E     |        log E       |
|    Insert     |     E     |        log E       |

----------------------------------------------------------------------------------------------------------------
## > Shortest Path
- source-sink: shortest path from one vertex to another
- single source: shortest path from one vertex to all others
- all pairs: shortest path between all pairs of vertices

---
### Dijkstra's algorithm
assume non-negative weights

#### Complexity

Cost
| PQ Implementation | insert | delMin | decreaseKey |  total  |
| ----------------- | ------ | ------ | ----------- | ------- |
|  Unordered Array  |   1    |   V    |      1      |   V^2   |
|    Binary Heap    | log V  | log V  |    log V    | E log V |

choose array implementation of PQ for dense graphs
choose binary heap implementation for sparse graphs

| Typical case | Worst Case | Extra Space |
| ------------ | ---------- | ----------- |
|   E log V    |  E log V   |      V      |

---
### Edge-weighted DAG algorithm
assume no cycles

- consider vertices in topological order
- add vertex to SPT and relax all outgoing edges


#### Complexity

Cost: (E+V) from topological sort

| Typical case | Worst Case | Extra Space |
| ------------ | ---------- | ----------- |
|   E + V      |    E + V   |      V      |

---
### Bellman-Ford algorithm
no assumptions (other than no negative cycles)

- repeat V times of relaxing all edges

#### Complexity

Cost: (E*V)

#### Regular Bellman-ford
| Typical case | Worst Case | Extra Space |
| ------------ | ---------- | ----------- |
|    E * V     |   E * V    |      V      |

#### Queue-based Bellman-ford
- if distTo[v] does not change in a pass i, no need to relax any outgoing edge from v in pass i+1
- maintain a queue of vertices whose distTo[] changed
  
| Typical case | Worst Case | Extra Space |
| ------------ | ---------- | ----------- |
|    E + V     |   E * V    |      V      |


----------------------------------------------------------------------------------------------------------------
## > String sorting algorithms
---
### Key - Indexed counting
Not inplace, Stable

Assume keys are integers in [0, R-1] (alphabet size R/ radix)
- as R is small, we can use the key as array index

#### Complexity
Sort array of N integers with values in [0, R-1]
| Time complexity | Space Complexity |
| --------------- | ---------------- |
| 	   N + R      |       log N      |

---
### Sorting LSD radix sort

Assume keys have same length D
- scan from right to left
- at each pass, use key-indexed counting on dth character to sort

#### Complexity
Sort array of N strings with W length with alphabet size R
|   Time complexity   | Space Complexity |
| ------------------- | ---------------- |
| W * (N + R) -> O(N) | (N + R) -> O(N)  |

---
### MSD radix sort
- Partition input into R pieces according to first character (use key-indexed counting to sort)
- Recursively sort all strings that start with same character

#### Complexity
Cost dependent on number of characters to examine
Sort array of N strings with W lengths with alphabet size R and depth of recursion D (length of longest prefix match)
|        Time complexity       | Space Complexity |
| ---------------------------- | ---------------- |
| Worst: ~W*N/ Avg: ~N log_R N |    ~ N + D*R     |

----------------------------------------------------------------------------------------------------------------
## > String sorting algorithms
Tries extended API
- Prefix match, find all keys in symbol table with starting prefix
- Longest prefix, find longest key in symbol that is the prefix of a given query string
- Get keys, iterate through all keys in sorted order
  
---
### R-way Tries
tree representation of symbol table
- each node represents one character, not full keys
- each node has exactly R children, one for each possible character
- root node has no character
- hit ends on node with non-null value, returning value

#### Complexity
Time:
	- Search hit: Need to examine all L characters in string (linear in L)
	- Search miss: on average, only a few characters examined (sublinear in L)
Space:
	- R null links at each leaf
	- Potentially many null links in intermediate node if strings do not share prefixes (sublinear space otherwise)

---
### 3-way Tries
tree representation of symbol table
- each node represents one character, not full keys
- each node has exactly 3 children: smaller (left), equal (middle), larger (right)

#### Complexity
Time:
	- as fast as hashing (for string keys), faster on search miss
Space:
	- Links ~ 4*N
	- Potentially many null links in intermediate node if strings do not share prefixes (sublinear space otherwise)

----------------------------------------------------------------------------------------------------------------
## > Substring Search

---
### Bruteforce
Use two indices i and j to scan text and pattern
- compare jth character in pattern with (i+j)th character in text
	- if characters match, move index j in pattern by 1
	- if not, move index i in the text by 1 and restart j index to the beginning
	  
#### Complexity
Worst case ~ N*M

Cost guarantee ~ N * M

---
### Knuth-Morris-Pratt algorithm
use DFA as a string-search machine
- start in initial state
- read one character at a time from input stream
- consult DFA transition table to know next state
- pattern found when final state

state number is the length of the longest prefix of pattern matched so far

DFA needs to be built from pattern
- initialise
	- create one state per character in pattern, plus final state
- match transitions
	- if in state j and next char c == pattern[j], go to state j+1
- mismatch transitions
	- if in state j and next char c != pattern[j], then last j-1 characters in input are pattern[1 ... j-1], followed by c
	- to fill in DFA[c][j], simulate having pattern[1..j-1] in input to the DFA, then take transition c

#### Complexity
Given pattern of length M, text of length N, and alphabet of radix R

Construction of DFA[][] ~ R*M (both space and time)
Substring search ~ M + N

Cost guarantee ~ N

---
### Boyer-Moore algorithm
scan pattern from right to left
- on character mismatch, skip as many as M (pattern length) text characters

Skip amounts
	- Case 1: mismatched character (text[i+j]) is not present in pattern
		-set i as 1 + mismatched spot (i -> i + j + 1)
	- Case 2: mismatched character in pattern
		-precompute index of rightmost occurence of mismatched character in pattern
		-skip i forward of (j- rightmost index)

#### Complexity
Preprocessing ~ M
Substring matching
Average case ~ N / M
Worst case ~ M * N