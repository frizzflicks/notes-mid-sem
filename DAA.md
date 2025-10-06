# Design and Analysis of Algorithm notes
## Concept of Algorithm
* An algorithm is a set of rules for carrying out calculation either by hands or a machine.
* An algorithm is aa set of computational steps that transform the input into the output.
* An algorithm is the process of alocating data into data structures.
* A finite set of instructiions which are used to solve a specific problem when run in an order is called an algorithm.
* An algorithm is an abstraction of a program to be run on a machine.
* An algorithm is a set of steps performed to solve a poroblem.
* It can be defined as a sequence of definite and effective instructions, while terminates with the production of correct output from the given input.

## Characteristics of algorithm
Every algorithm should follow the following chatracteristics:
### Input
* An algorithm should have zero or more inputs.
* The inputs are taken from a specified set of subjects.

### Output
* An algorithm may have one or more outputs.
* Output is a quantity which has a specified relation with the input.

### Finiteness
* An algorithm must terminate after a countable number of steps.
* In some cases the repetition number may be larger.
* If a procedure is able to resolve in a finite number if steps, it is called a computational method.

### Definiteness
* An algorithm should have precisely defined steps.
* Every step of your algorithm should be **crystal clear**, not vague.
* No “do it somehow” type of instructions.
* A computer (or even a human following blindly) should be able to understand exactly what to do.
* If natural language sounds confusing, you can write steps using **math symbols or pseudo-code**, so it’s unambiguous like programming code.

### Effectiveness
* An algorithm is generally expected to effective.
* Means the steps should be sufficiently basic, so that it may be possible for a man to resolve them.

### Algorithm Specification Template

1. **Problem Definition:**
   State what the algorithm is supposed to do.

2. **Input:**
   Clearly mention what kind of data the algorithm will take.

3. **Output:**
   What result the algorithm should produce.

4. **Steps (Procedure):**
   Numbered list of precise steps (in plain English, pseudocode, or both).

***

### **Example: Binary Search**

1. **Problem Definition:**
   To find the position of a given element (key) in a sorted list using Binary Search.

2. **Input:**

   * A sorted array `A[1..n]` of `n` elements
   * A key element `x`

3. **Output:**

   * Index `i` such that `A[i] = x`, if present
   * Otherwise, report “Not Found”

4. **Steps:**

   1. Set `low = 1`, `high = n`.

   2. While `low ≤ high`:
      a. Set `mid = (low + high) / 2`.
      b. If `A[mid] = x`, return `mid`.
      c. If `A[mid] > x`, set `high = mid – 1`.
      d. Else, set `low = mid + 1`.

   3. Return “Not Found”.
  
   ***

## Performance Analysis

There are many criteria upon which we may judge a program:

* Does the program meet the original specifications of the task?
* Does it work correctly?
* Does the program contain documentation about its use?
* Is the program's code readable?
* Is the program's code modular

However we could judge the program's performace using a more concrete criteria:

* Does the program efficiently use primary and secondary memory?
* Is the program's running time acceptable for the task?

### Space Complexity
The _space complexity_ refer to the amount of memory a function needs to run to completion
* The space needed by programs is a sum of following components:

- **Fixed Space Requirements:** This component refers to the space requirements that do not depend on the size of the program's inputs and outputs.The fixed requirements include the instruction space, space for simple variables, fixed size structured variables, and constants.
  
- **Variable Space Requirements:** : This component consists of the space needed by structured variables whose size depends on the particular instance, _I_, of the problem being solved. It also includes the additional space required when a function uses recursion. The variable space requirement of a program _P_ working on an instance _I_ is denoted `Sp(I)`.

We can express the total space requirement S (P) of any program as:
$$S(P) = c + Sp(I)$$
where $c$ is a constant representing the fixed space requirements.

* When analyzing the space complexity of a program we are usually concerned with only the variable space requirements.
* This is particularly true when we want to compare the space complexity of several programs.

### Time Complexity
The time complexity of a program is the amount of computer time that it needs to run to completion.

* The total time taken by a program `P` is:
  **Tₚ = Compile Time + Run Time (Execution Time)**

#### 1. Compile Time

* Similar to **fixed space component** → does not depend on input/instance.
* Once program correctness is verified, we may run it many times **without recompiling**.
* So, compile time is usually ignored in performance analysis.

#### 2. Execution Time (Run Time)

* The main concern in algorithm analysis.
* Depends on:
  * The **compiler** (how source code is translated to machine code).
  * The **operations performed** in the program.

Example:
For input size `n`,

$$
Tₚ(n) = c₁·ADD(n) + c₂·SUB(n) + c₃·LDA(n) + c₄·STA(n)
$$

where:

* `ADD(n)`, `SUB(n)`, `LDA(n)`, `STA(n)` → number of additions, subtractions, loads, stores.
* `c₁, c₂, c₃, c₄` → constant time taken per operation.

#### 3. Practical Difficulty

* Getting exact `Tₚ` is **hard** (requires deep compiler-level knowledge).

#### 4. Approaches to Estimate Run Time

1. **Use system clock** → run the program and measure execution time.
2. **Operation counting** → count number of basic steps/operations.

   * Machine-independent estimate.
   * Requires deciding what counts as a “step.”

## Asymptotic Notations (O, Ω, Θ)
* Exact step counts of programs are hard to determine and are often unnecessary.
* Step counts are unexact: one step could be `x = y` or `x = y + z - x/z` etc.
* The goal is to compare the growth rates as the input size of algorithm `n` increases.
* For large n, knowing approximate growth is enough to predict which program runs faster.
* The **break-even point** `k` is the input size `n` after which one algorithm consistently outperforms another; knowing the exact constants is usually not needed.

### 1. The Big - Oh Notation $(O)$ - _Upper Bound, Worst Case_
$$
f(n) \in O(g(n)) \text{ if there exist constants } c > 0 \text{ and } n_0 \text{ such that } f(n) \le c \cdot g(n) \text{ for all } n \ge n_0.
$$
* Algorithm will take at most O(g(n)) time for large n.
Common types:

$O(1)$ → constant
$O(log n)$ → logarithmic
$O(n)$ → linear
$O(n log n)$ → log-linear
$O(n²)$ → quadratic
$O(n³)$ → cubic
$O(2ⁿ)$ → exponential

![15f5ad4f9aaa9a622e08e69100c2e60d.png](./15f5ad4f9aaa9a622e08e69100c2e60d.png)

### 2. Omega Notation $(Ω)$ – _Lower Bound / Best Case_

$f(n)∈Ω(g(n)) \text{ if there exist constants } c>0,n_0​ \text{ such that } f(n)≥c⋅g(n) \text{ for all } n≥n_0​$

* Algorithm will take **at least** $Ω(g(n))$ time for large `n`.

  ![e213274b17dc715714342bbdcbbbb000.png](./e213274b17dc715714342bbdcbbbb000.png)

### 3. Theta Notation (Θ) – _Tight Bound / Average Case_

$f(n)∈Θ(g(n)) \text{ if there exist constants } c1​,c2​>0,n_0​ \text{ such that } c1​⋅g(n)≤f(n)≤c2​⋅g(n) \text{ for all } n≥n_0​$

Meaning:

* Algorithm grows **exactly like g(n)** for large `n`.
* More precise than $O$ or $Ω$ because it gives **both upper and lower bounds**.
![3721ad6ea3b23d86ffa06fbf541194d8.png](./3721ad6ea3b23d86ffa06fbf541194d8.png)

***

## Divide and Conquer
* In this approaach we solve a problem recursively by applying three steps:
- **Divide**: Break the problem into several sub-problems of smaller size.
- **Conquer**: Solve the problem recursively.
- **Merge**: Combine the solution based on a condition to create a solution to the original problem.

### General Algorithm:
```dart
Algorithm DC(p)
{
	if small(p)
    then return S(P)
    else
    {
    	divide p into smaller instances P1, P2, P3, ... Pn.
        Apply DC to each sub - problem
        Return DC(P1) + DC(P2) + DC(P3) + ... + DC(Pn) where + is an operator.
    }
}
```

Let a recurrence relation is expressed as 
$$T(n)= ϴ(1), \text{ if } n<=C \text{ aT } (n/b) + D(n)+ C(n)$$ where n = input size, a = no. Of sub-problems, b= input size of the subproblems.

#### Binary Search
```dart

Function BinarySearch(list, searchnum, left, right):
	if left > right:
        return -1 //Element not found
	
    middle = (left + right)/2

    if list[middle] == searchnum:
		return middle  //Element found

    else if list[middle] > searchnum:
		return BinarySearch(list, searchnum, left, middle - 1) //Search the left half
    else 
        return BinarySearch(list, searchnum, middle + 1, right) //Search the right half

```

**Time Complexity:** $O(logn)$
**Recurrence:** $T(n) = T(n/2) + O(1)$
**Work per level:** $O(1)$ (dividing and selecting one part from the two)
**Number of levels:** $log_2n$ 
**Total Work:** $O(1) * logn = O(logn)$

Example:

![im1.jpg](im1.jpg)

#### Finding max or min 
##### Min:

```dart

Function FindMin(arr, low, high):
	if low == high: //one element only
		return arr[low]

    if high = low + 1: //if only 2 elements
		return min(arr[low], arr[high])

    mid = (low + high) / 2

    min1 = FindMin(arr, low, mid)
    min2 = FindMin(arr, mid + 1, high)

    overall_min = min(min1, min2)

    return overall_min
            
```
**Complexity:** $O(n)$
**Recurrence:** $T(n) = 2T(n/2) + O(1)$
**Work per level:** $O(2^k)$ (dividing into two parts each step)
**Number of levels:** $log_2n$ 
**Total Work:** Sum across all levels:
$T(n) = \sum_{k=0}^{\log_2 n} W_k = \sum_{k=0}^{\log_2 n} O(2^k)$

This is a **geometric series**:
$1+2+4+⋯+n=2n−1≈O(n)$

![im2.jpg](im2.jpg)

#### Quick Sort`

```dart
QUICKSORT (array, start, end):
	if start < end:
		pivotIndex = PARTITION(array, start, end)
        QUICKSORT(array, start, pivotIndex - 1) // sort left subarray
        QUICKSORT(array, pivotIndex + 1, end) // sort right subarray

PARTITION (array, start, end):
	pivot = array[end] // choose last element as pivot
    i = start - 1
    for j = start to end - 1:
		if array[j] < pivot:
			i = i + 1
            swap array[i] <-> array[j]
    swap array[i+1] <-> array[end] // place pivot at right place
    return i + 1 // pivot index
```

QuickSort is a **divide-and-conquer algorithm**.
* **Divide:** Pick a pivot (here, the last element) and partition the array into two subarrays:
  * Left subarray: all elements ≤ pivot
  * Right subarray: all elements ≥ pivot
* **Conquer:** Recursively sort the left and right subarrays.
* **Combine:** Nothing to do — arrays are sorted **in-place**.

##### **Partition Function**

* Picks the **last element as pivot**.
* Moves all elements ≤ pivot to the left, others to the right.
* Returns pivot’s final position `q`.
* Work done = **Θ(n)** for a subarray of size n (each element compared once).

##### Recurrence Relations

Let’s define **$T(n) = \text{time to sort n elements}$**.

##### Worst Case

* Happens when **pivot is the smallest or largest element** → completely unbalanced split:
  * One subarray = size $n−1$
  * Other subarray = size 0
$$T(n)=T(n−1)+T(0)+Θ(n)=T(n−1)+Θ(n)$$
* Solve it:
$$T(n)=n+(n−1)+(n−2)+…+1=O(n2)$$
> Intuition: Each partition scans the whole array, but only reduces size by 1 → quadratic behavior.

***

##### Best Case

* Pivot splits array **exactly in half** every time:
  * Subarrays = $n/2$ and $n/2$
  
$$T(n)=2T(n/2)+Θ(n)$$

* Solve with Master Theorem / recursion tree:
$$T(n)=O(nlogn)$$
> Intuition: Work per level = Θ(n), number of levels = log₂ n → total = n log n

***

##### Average / Balanced Case

* Pivot splits array roughly **constant ratio**, e.g., 9:1:

$$T(n)=T(9n/10)+T(n/10)+Θ(n)$$

* Recursion tree depth = $O(log n)$ (because each time array reduces by constant fraction)
* Work per level = $Θ(n)$
* **Total work = $O(n log n)$**

> Key insight: The exact split ratio changes the constants but **not the asymptotic complexity**.
> 
![im3.jpg](im3.jpg)

##### Selection of Pivot Element in QuickSort

The pivot element is the value around which the array is partitioned. The choice of pivot significantly affects QuickSort’s performance.

1️. **Role of Pivot**

Partition the array into two subarrays:
_Left subarray_: all elements ≤ pivot
_Right subarray_: all elements ≥ pivot

Recursive sorting of these subarrays eventually sorts the whole array.

2️. **Common Methods to Choose Pivot**

* First element of the array
> Simple, but can be bad for already sorted arrays → worst-case O(n²)

* Last element of the array

> Used in Lomuto partition
> Same risk as above

* Random element

> Pick a random index as pivot
> Reduces chance of worst-case performance
> Gives expected O(n log n) running time

* Median-of-three

> Pick first, middle, last elements and take their median
> Improves balance of partitions
> Often used in practical implementations

* True median

> Guarantees perfectly balanced split
> Expensive to compute → rarely used in practice

* Effect on Complexity

| Pivot Choice    | Best Case  | Worst Case          | Expected Case |
| --------------- | ---------- | ------------------- | ------------- |
| First / Last    | O(n log n) | O(n²)               | O(n log n)    |
| Random          | O(n log n) | very unlikely O(n²) | O(n log n)    |
| Median-of-three | O(n log n) | O(n²)               | O(n log n)    |
| True Median     | O(n log n) | O(n log n)          | O(n log n)    |

> Key idea: The closer the pivot is to the true median, the more balanced the partitions → faster sorting.

***

## Greedy Algorithms 

### Introduction

The **Greedy method** is a strategy for solving _optimization_ problems.
An optimization problem requires finding the best solution (maximum or minimum) that satisfies a set of constraints.

Greedy algorithms build the solution step by step.
At each step, they select the option that looks **best at the moment** (locally optimal choice).
Once a choice is made, it is **never changed later**.

***

### Feasible vs. Optimal Solution

* A solution is **feasible** if it satisfies all constraints of the problem.
* Among feasible solutions, the one that optimizes the objective function (maximum or minimum) is called the **optimal solution**.

***

### **Characteristics of Greedy Approach**

1. **Feasibility** – Every step must satisfy explicit and implicit constraints.

   * _Explicit constraints:_ Output must use only elements from the input set.
   * _Implicit constraints:_ Must satisfy the problem’s objective function.

2. **Locally Optimal Choice** – At each step, the algorithm selects the best candidate available without considering future consequences.

3. **Irrevocability (Unalterable)** – Once a decision is taken, it cannot be undone.

4. **Greedy-Choice Property** – A global optimum can be reached by choosing local optima at each step.

5. **Optimal Substructure** – An optimal solution to the overall problem contains optimal solutions to its subproblems.

***

### **General Strategy of a Greedy Algorithm**
`isfit`

1. **Initialization** – Start with an empty solution set.
2. **Selection** – At each step, choose the best candidate according to a selection criterion.
3. **Feasibility Check** – If adding the candidate keeps the solution feasible, include it.
4. **Irrevocability** – Do not reconsider discarded candidates.
5. **Termination** – Repeat until the solution is complete or no more candidates remain.

```dart
Greedy(A, n)
{
    solution = ∅

    for i = 1 to n do
    {
        x = Select(A)              // choose the best candidate
        if Feasible(x) then        // check if adding x is valid
            solution = solution ∪ {x}
    }

    return solution
}

```

* `Select(A)` → picks the _locally best_ candidate according to some greedy strategy.
* `Feasible(x)` → checks whether adding this choice keeps the solution valid (no violation of constraints).
* `solution` → keeps building the final answer step by step.
* The loop → goes over the set of candidates, trying to construct the solution.

***

### **Advantages**

* Simple to design and implement.
* Efficient in terms of time complexity (often **O(n log n)** due to sorting).
* Works well when the greedy-choice property holds.

***

### **Disadvantages**

* Does not always guarantee an optimal solution.
* Can fail when local decisions don’t lead to a global optimum.
* Needs mathematical proof to confirm correctness.

***

### **Applications**

* Scheduling problems
* Minimum spanning trees (Prim’s, Kruskal’s algorithms)
* Huffman coding
* Graph coloring, shortest paths (Dijkstra’s)

***

 So, in essence:
The **Greedy method** is a problem-solving paradigm where we repeatedly make the **locally optimal choice** with the hope of reaching the **globally optimal solution**.

***

## Fractional Knapsack Problem 

### Definition

* We are given:

  * **n objects**, each with:

    * Profit: $(p_i)$
    * Weight: $(w_i)$
  * A knapsack with **capacity (M)**.
* Objective: **maximize profit** while keeping total weight ≤ (M).
* Key difference from 0/1 Knapsack:
   Here, we can take **fractions of an item** (i.e., $(0 \leq x_i \leq 1)$).

***

### Mathematical Formulation
$$\text{Maximize } Z = \sum_{i=1}^n p_i x_i$$

Subject to:
$$\sum_{i=1}^n w_i x_i \leq M$$
$$0 \leq x_i \leq 1, \quad 1 \leq i \leq n$$

Where:

* ($p_i$) = profit of item i
* ($w_i$) = weight of item i
* ($x_i$) = fraction of item i selected

***

### Greedy Strategy (Optimal Method)

1. Compute **profit/weight ratio** for each item:
   $$\frac{p_i}{w_i}$$
2. Arrange items in **descending order of ratio**.
3. Pick items one by one into knapsack:

   * If item fits fully → take it.
   * If item does not fit fully → take the possible fraction.

 This greedy approach always gives **optimal solution** for fractional knapsack.

***

### Example

Given:

* (n = 3)
* Profits = ({25, 24, 15})
* Weights = ({18, 15, 10})
* Capacity (M = 20)

**Step 1**: Compute ratios

* Item 1: (25/18 $\approx$ 1.39)
* Item 2: (24/15 = 1.6)
* Item 3: (15/10 = 1.5)

Order → Item 2 > Item 3 > Item 1

***

### Feasible Solutions

| Solution No | x1 | x2   | x3  | ∑wi·xi | ∑pi·xi |
| ----------- | -- | ---- | --- | ------ | ------ |
| 1           | 1  | 2/15 | 0   | 20     | 28.2   |
| 2           | 0  | 2/3  | 1   | 20     | 31.0   |
| 3           | 0  | 1    | 1/2 | 20     | 31.5   |

* **Best solution = 3 (Profit = 31.5)**

***

### Key Points for Exams

* Fractional knapsack is solved using **Greedy algorithm**.
* Always arrange items by **profit/weight ratio**.
* Unlike 0/1 knapsack, fractions are allowed → greedy gives **optimal** result.
* If fractions were **not allowed** (0/1 case), greedy doesn’t always give optimal.

***

 **Final Answer for Example:**
Maximum profit = **31.5** at solution (x1=0, x2=1, x3=1/2).

***

## Minimum Cost Spanning Tree
* Let  $G = (V, E)$ be the graph where $V$ is the set of vertices, $E$ is the set of edges and $|V|= n$.
* The spanning tree $G'= (V, E')$ is a sub graph of $G$ in which all the vertices of graph $G$ are connected with **minimum number of edges**.
* The minimum number of edges required to collect all the vertices of a graph $G$ are $n – 1$.
* Spanning tree plays a very important role in designing efficient algorithms.
* A greedy method to obtain the minimum spanning tree would construct the tree edge by edge, where each edge is chosen accounting to some optimization criterion.
* An obvious criterion would be to choose an edge which adds a minimum weight to the total weight of the edges selected so far.
* There are two ways in which this criterion can be achieved.
  
* **Prim’s Algorithm**
  * Start with a set of edges that **always forms a tree**.
  * At each step, **add the minimum-weight edge** that **keeps the set a tree**.
  * This guarantees that the resulting tree is a **minimum cost tree**.

* **Kruskal’s Algorithm**
  * Consider all edges in **non-decreasing order of weight**.
  * At each stage, select edges such that it is **possible to eventually complete a tree**.
  * The selected set **may not be a tree** at intermediate stages.
  * This also results in a **minimum cost tree**

## Kruskal algorithm
***

**Overview:**

* Starts with **all edges sorted in non-decreasing order of weight**.
* Builds MST by **repeatedly adding the smallest edge** that **does not form a cycle**.

***

### Step-by-Step Procedure

1. **Initialization:**

   * Each vertex is in its **own tree** (forest).
   * MST edge set `A = ∅`.

2. **Iterate through edges in increasing order of weight:**

   * Consider edge `(u, v)`.
   * If `(u, v)` connects vertices in **different trees**, add `(u, v)` to MST and **merge the trees**.
   * If `(u, v)` connects vertices in the **same tree**, discard it (to avoid cycle).

3. **Stop:**

   * When all vertices are connected (single tree) → MST is complete.

***

### Pseudocode

```dart

T - {};
while (T contains less than n-1 edges && E is not empty) {
	choose a least cost edge (v,w) from E;
	delete (v,w) from E; 
if {(v,w) does not create a cycle in T)
	add (v,w) to T;
else
	discard (v,w);
}
if (T contains fewer than n-1 edges)
	print("No spanning tree\n");

```

***

![f838852f6f11c69928afd0c719349f90.png](./f838852f6f11c69928afd0c719349f90.png)
***

## Kruskal's Algorithm Trace

| Edge | Weight | Result | Figure |
| :---: | :---: | :---: | :---: |
| --- | --- | initial | Figure 6.25(b) |
| (0, 5) | 10 | added to tree | Figure 6.25(c) |
| (2, 3) | 12 | added | Figure 6.25(d) |
| (1, 6) | 14 | added | Figure 6.25(e) |
| (1, 2) | 16 | added | Figure 6.25(f) |
| (3, 6) | 18 | discarded | |
| (3, 4) | 22 | added | Figure 6.25(g) |
| (4, 6) | 24 | discarded | |
| (4, 5) | 25 | added | Figure 6.25(h) |
| (0, 1) | 28 | not considered | |

 **Exam Tip:**

* Kruskal is **edge-based**, merges trees.
* Prim is **vertex-based**, grows a single tree from a start vertex.

***

### Time Complexity of Kruskal’s Algorithm

1. **Initialization:**  
   - Create `n` trees from `n` vertices → **O(n)**.  

2. **Heap Creation:**  
   - Build a min-heap of edges using heapify → **O(n)**.  
   - The **smallest weight edge** is at the root.  

3. **Edge Processing:**  
   - Delete edges one by one from heap.  
   - For each edge:  
     - Add to MST if it **connects different trees**.  
     - Discard if it **forms a cycle**.  
   - Edge deletion and union-find operations → **O(n log n)**.  

***

### Total Time Complexity
$$\text{O(n) + O(n) + O(n log n)} = O(n \log n)$$
***

   **Exam Tip:**  
- Kruskal is efficient for **sparse graphs**.  
- Heap + disjoint-set ensures **fast edge selection and cycle detection**.  

***

## Prim’s Algorithm 

### Concept

* Prim’s algorithm builds an MST by **growing a single tree**:

  * Start with the **minimum weight edge**.
  * Repeatedly **add the smallest edge** connecting a vertex in the tree to a vertex outside.
* Each node `j` has an associated **near(j)** pointer:[^1]

  * `near(j) = 0` → node is included in the tree.
  * Otherwise, `near(j)` points to the **closest node already in the tree**.

***

### Steps of the Algorithm

1. **Initialization:**

   * Find edge `(k, l)` with **minimum weight** → add to tree `T`.
   * For all other vertices `i`, set `near[i]` = closer of `k` or `l`.
   * Set `near[k] = near[l] = 0`.

2. **Iterative Steps:**
   Repeat for remaining `n-2` edges:

   * Select vertex `j` with `near[j] ≠ 0` and **minimum weight** `wt[j, near[j]]`.
   * Add edge `(j, near[j])` to MST.
   * Set `near[j] = 0` (vertex included).
   * Update `near[k]` for all remaining vertices `k`:
     [
     \text{if } near[k] ≠ 0 \text{ and } wt[k, near[k]] > wt[k, j] \text{ then } near[k] = j
     ]

3. **Termination:**

   * Stop when **all vertices are included**.
   * If `minwt = ∞` → No spanning tree exists.

***

### Pseudocode

```dart

T = ();
TV = {0}; /* start with vertex 0 and no edges */
while (T contains fewer than n-1 edges) {
    let (u, v) be a least cost edge such that u ∈ TV and
    v ∉ TV;
    if (there is no such edge)
        break;
    add v to TV;
    add (u, v) to T;
}
if (T contains fewer than n-1 edges)
    print("No spanning tree\n");

```

### Example Step-wise Construction

Weighted Graph Example (edges with weights):

![0f4457866f801a37f1ce0f940a723aaa.png](./0f4457866f801a37f1ce0f940a723aaa.png)
![9e72c3da1dfe3dd5d5b738b61afcb150.png](./9e72c3da1dfe3dd5d5b738b61afcb150.png)


### Prim's Algorithm Trace

| **Step** | **Tree Vertices (TV)** | **Candidate Edges (from TV to V \ TV)** | **Edge Chosen (Least Cost)** | **Weight** |
| :---: | :---: | :--- | :---: | :---: |
| **Initial** | $\{0\}$ | (0, 5), (0, 1) | **(0, 5)** | 10 |
| **1** | $\{0, 5\}$ | (0, 1) [W: 28], (5, 4) [W: 25] | **(5, 4)** | 25 |
| **2** | $\{0, 5, 4\}$ | (0, 1) [W: 28], (4, 6) [W: 24], (4, 3) [W: 22] | **(4, 3)** | 22 |
| **3** | $\{0, 5, 4, 3\}$ | (0, 1) [W: 28], (4, 6) [W: 24], (3, 6) [W: 18], (3, 2) [W: 12] | **(3, 2)** | 12 |
| **4** | $\{0, 5, 4, 3, 2\}$ | (0, 1) [W: 28], (4, 6) [W: 24], (3, 6) [W: 18], (2, 1) [W: 16] | **(2, 1)** | 16 |
| **5** | $\{0, 5, 4, 3, 2, 1\}$ | (4, 6) [W: 24], (3, 6) [W: 18], (1, 6) [W: 14] | **(1, 6)** | 14 |
| **Final** | $\{0, 1, 2, 3, 4, 5, 6\}$ | **MST Complete** | | |

**Minimum Spanning Tree Edges:**

$$T = \{(0, 5), (5, 4), (4, 3), (3, 2), (2, 1), (1, 6)\}$$

**Total Minimum Cost:**

$$10 + 25 + 22 + 12 + 16 + 14 = 99$$
***

### Time Complexity

1. First for-loop (initialize near) → **O(n)**
2. Second for-loop (select remaining n-2 edges) → **O(n)**
3. Third for-loop (update near for each node inside second loop) → **O(n²)**

**Overall time complexity:**
$$\mathbf{O(n^2)}$$
***

 **Exam Tips:**

* Prim’s algorithm is **vertex-based** → grows a single MST tree.
* Edge selection depends on **current tree vertices**.
* **Near array** keeps track of the closest vertex already in the MST.

## Shortest Path Problem

Let us consider a number of cities connected with roads and a traveler wants to travel form his home city A to the destination B with a minimum cost. So the traveler will be interested to know the following:
* Is there a path from city A to city B?
* If there is more than one path from A to B, which is the shortest or least cost path?
  
Let us considerthe graph $G = (V, E)$, a weighting function $w(e)$ for the edges in $E$ and a source node $v_0$. The problem is to determine the shortest path from $v_0$ to all the remaining nodes of $G$. The solution to this problem is suggested by E.W. Dijkstra and the algorithm is popularly known as `Dijkstra‟s algorithm`.

***

### Dijkstra’s Single-Source Shortest Path Algorithm

This algorithm finds **the shortest paths one by one** from a **single source vertex** (v₀) to all other vertices in a **weighted graph** (with non-negative edge weights).

Let $S$ be the set of vertices for which the **shortest paths have already been found**.

For each vertex $z$ not in $S$,
`dist[z]` represents the **current known shortest distance** from $v₀$ to $z$, considering only the vertices in $S$.

At each step:

1. Choose the vertex $u ∈ S$ with the **smallest distance value** (`dist[u]`).

2. For each adjacent vertex $z$ $\notin$ $S$:

   * If `dist[z] > dist[u] + w(u, z)`,
     then **update** `dist[z] = dist[u] + w(u, z)`
     and **set the predecessor** of $z$ to $u$.

3. Add $u$ to $S$ (marking it as finalized).

The process repeats until shortest paths to all vertices are determined.

### Algorithm Dijkstra (v0, W, dist, n)
```dart

function Dijkstra(Graph, source)
    for each vertex v in Graph.Vertices:
        dist[v] ← INFINITY
        prev[v] ← UNDEFINED
        add v to Q                     # Q = all unvisited vertices

    dist[source] ← 0                   # distance to itself = 0

    while Q is not empty:
        u ← vertex in Q with min dist[u]  # choose closest unvisited vertex
        remove u from Q

        for each neighbor v of u still in Q:
            alt ← dist[u] + Graph.Edges(u, v)
            if alt < dist[v]:              # if new path is shorter
                dist[v] ← alt              # update shortest distance
                prev[v] ← u                # store path predecessor

    return dist[], prev[]

```
The time complexity of the algorithm is $O(n^2)$.

### Example:

![304d9fbde8581289ee951969308cdc88.png](./304d9fbde8581289ee951969308cdc88.png)

We’ll assume **B** is the **source node**, since in the first round its distance = 0.

***

### Step 0: Initial Setup

| Vertex         | Distance | Previous |
| -------------- | -------- | -------- |
| A              | ∞        | —        |
| **B (source)** | **0**    | —        |
| C              | ∞        | —        |
| D              | ∞        | —        |
| E              | ∞        | —        |
| F              | ∞        | —        |

***

### Step 1: Start from B (distance 0)

From **B**, the edges are:

* B → A = 10
* B → C = 8
* B → D = 2
* B → E = 6

Update distances:

| Vertex | Distance | Previous |
| ------ | -------- | -------- |
| A      | 10       | B        |
| **B**  | **0**    | —        |
| C      | 8        | B        |
| D      | 2        | B        |
| E      | 6        | B        |
| F      | ∞        | —        |

Chosen next: **D** (smallest dist = 2)

***

### Step 2: Visit D (dist = 2)

Edges from D:

* D → A = 4
* D → B = 2
* D → E = 6

Check for shorter paths:

* A via D: 2 + 4 = **6** (better than 10)
* E via D: 2 + 6 = 8 (not better than 6)

 Update:

| Vertex | Distance | Previous |
| ------ | -------- | -------- |
| **A**  | **6**    | D        |
| B      | 0        | —        |
| C      | 8        | B        |
| D      | 2        | B        |
| E      | 6        | B        |
| F      | ∞        | —        |

Next: **A** or **E** (tie, both = 6). Let’s take A.

***

### Step 3: Visit A (dist = 6)

Edges from A:

* A → B = 10
* A → D = 4

No updates (both already smaller).

Next: **E (6)**

***

### Step 4: Visit E (dist = 6)

Edges from E:

* E → B = 6
* E → C = 1
* E → D = 6
* E → F = 12

Check:

* C via E: 6 + 1 = **7** (better than 8)
* F via E: 6 + 12 = **18**

Update:

| Vertex | Distance | Previous |
| ------ | -------- | -------- |
| A      | 6        | D        |
| B      | 0        | —        |
| **C**  | **7**    | E        |
| D      | 2        | B        |
| E      | 6        | B        |
| **F**  | **18**   | E        |

 Next: **C (7)**

***

### Step 5: Visit C (dist = 7)

Edges from C:

* C → B = 8
* C → E = 1
* C → F = 5

Check:

* F via C: 7 + 5 = **12** (better than 18)

Update:

| Vertex | Distance | Previous |
| ------ | -------- | -------- |
| A      | 6        | D        |
| B      | 0        | —        |
| C      | 7        | E        |
| D      | 2        | B        |
| E      | 6        | B        |
| **F**  | **12**   | C        |

***

### Final Shortest Distances (from B)

| Vertex | Distance | Path          |
| ------ | -------- | ------------- |
| A      | 6        | B → D → A     |
| B      | 0        | —             |
| C      | 7        | B → E → C     |
| D      | 2        | B → D         |
| E      | 6        | B → E         |
| F      | 12       | B → E → C → F |

***

![476ecb34561cb3dc34bcb3d52bd21171.png](./476ecb34561cb3dc34bcb3d52bd21171.png)

|       |  A  | B   | C   | D   | E   | F   |
| ----- | --- | --- | --- | --- | --- | --- |
| **A** | Inf | 10  | Inf | 4   | Inf | Inf |
| **B** | 10  | Inf | 8   | 2   | 6   | Inf |
| **C** | Inf | 8   | Inf | Inf | 1   | 5   | 
| **D** | 4   | 2   | Inf | Inf | 6   | Inf | 
| **E** | Inf | 6   | 1   | 6   | Inf | 12  | 
| **F** | Inf | Inf | 5   | Inf | 12  | Inf |
***

### **Search Process**

| **Round** | **A** | **B** | **C** | **D** | **E** | **F** |
|-----------|-------|-------|-------|-------|-------|-------|
| **1**     | 10    | 0     | 8     | 2     | 6     | ∞     |
| **2**     | 6     | 0     | 8     | 2     | 6     | ∞     |
| **3**     | 6     | 0     | 8     | 2     | 6     | ∞     |
| **4**     | 6     | 0     | 7     | 2     | 6     | 18    |
| **5**     | 6     | 0     | 7     | 2     | 6     | 12    |
| **6**     | 6     | 0     | 7     | 2     | 6     | 12    |

***

## Multistage Graphs
