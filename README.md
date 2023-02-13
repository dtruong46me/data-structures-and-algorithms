# Data Structures and Algorithms

## Prim's Algorithm to find Minimum Spanning Tree

```
Step 1: Initialize
    V(MST) = {u}
    V = V\{u}
    MST = empty; d = 0

Step 2: Loop
    while (V is not empty) do:
        e = (x,y)  // The minimum edge such that x in V and y in V(MST)
        MST = MST + {e}  // Add e to the MST
        d = d + d(e)
        V(MST) = V(MST) + {x}
        V = V \ {x}

Step 3: Return
```

## KrusKal's Algorithm to find Minimum Spanning Tree

```
Step 1: Initialize
    MST = empty
    E : The set of edges in graph G
    d(MST) = 0 

Step 2: Sort    
    <Sort the edge in increasing order>

Step 3: Loop
    while (|MST| < n-1) and (E is not empty) do:
        e = <The minimum edge in E>
        E = E \ {e}
        if (MST + {e} do not creat a cycle) then:
            MST = MST + {e}
            d(MST) = d(MST) + d(e)

Step 4: Return
```

## Breath First Search

```
BFS(u):  // `u` is the start_node
Step 1: Initialize
    queue = empty
    queue.push(u)
    visited[u] = 1

Step 2: Loop
    while (queue is not empty) do:
        s = queue.pop()  Remove element in the first of queue
        for each `t` in ADJ(s) do:
            if (visited[u] = 0) then:
                visited[u] = 1
                queue.push(t)

Step 3: Return
```

## Depth First Search

```
DFS(u):  // `u` is the start_node
Step 1: Initialize
    stack = empty
    stack.push(u)
    visited[u] = 1  // Marking this edge is visited

Step 2: Loop
    while (stack is not empty) do:
        s = stack.pop()  // Remove the element in the first of the stack
        for each `t` in ADJ(s) do:
            if (visited[t] = 0) then:
                visited[t] = 1
                stack.push(s)
                stack.push(t)
                break    // Only take 1 vertex `t`

Step 3: Return
```

## Dijkstra's Algorithm to find the shortest path in the Graph

```
Dijkstra(start_node, end_node):
Step 1: Initialize
    distances[start_node] = 0
    distances[<other nodes>] = INF
    V = V \ {start_node}   // unvisited_nodes

Step 2: Loop
    while (V is not empty) do:
        u = select a node in V having minimum d[u]
        V = V \ {u}

        for each `v` in V do:
            if (distances[v] > distances[u] + w[u, v]) then:
                distances[v] = distances[u] + w[u,v]
                previous[v] = u

Step 3: Return
    return (distances[s], previous[s])
```

## Bellman-Ford's Algorithm

```
Bellman-Ford(s):    s is the start_node
Step 1: Initialize
    for `v` in V:
        d[v] = A[s][v]
        preveous[v] = s

Step 2: Loop 
    d[s] = 0, k = 1
    while (k < n-2) do:
    for `v` in V do:
        for `v` in V do:
            if d[v] > d[u] + ADJ[u,v]
                d[v] = d[u] + ADJ[u,v]
                preveous[v] = u
```

## Floyd's Algorithm

```
Step 1: Initialize
    for u in V do:
        for v in V do:
            d[u,v] = w[u,v]

Step 2: Loop
    for u in V do:
        for v in V do:
            for k in V do:
                if d[v,u] + d[u,k] < d[v,k] then:
                    d[v,k] = d[v,u] + d[u,k]

Step 3: Return
    return d[u,v]  // The length of a shortest path between u and v
```

## PreOrder, InOrder, PostOrder Travesal
1. PreOrder
```
PreOrder(T):
    r := root of T
    <visit r>
    for each child c of r from left to right:
        T(c) := subtree with c as its root
        PreOrder(T(c))
```

2. InOrder
```
InOrder(T):
    r := root of T
    if r is a leaf then: 
        <visit r>
    else:
        l := first child of r from left to right
        T(l) := subtree with l as its root
        InOrder(T(l))
        <visit r>
        for each child c of r except for l from left to right:
            T(c) := subtree with c as its root
            InOrder(T(c))
```

3. PostOrder
```
PostOrder(T):
    r := root of T
    for each child c of r from left to right:
        T(c) := subtree with c as its root
        PostOrder(T(c))
    <visit r>
```

## Detect cycle on Undirected Graph
 *Method 1 : Using Depth First Search*
 ```
 DFS(u, parent):
    visited[u] = 1
    for (v in ADJ[u]) do:
        if (visited[v] = 0) then:
            if (DFS(v,u)) then:
                return 1
        else if (v is not parent) then:
            return 1
    return 0
 ```
 *Method 2 : Using DisjointSet Algorithm*
 ```
 ```

## Sorting Algorithms
1. Bubble Sort 

*Idea : For each iteration, this method will take the maximum element to the end of array A.*
```
BubbleSort(A):
    for (i = 1,2,...N) do:
        for (j = 1,2,...N-i) do:
            if A[j] > A[j+1] then:
                swap(A[j], A[j+1])
            // Đẩy phần tử lớn hơn xuống cuối cùng của mảng
```

2. Selection Sort

*Idea : Select the minimum is the first, second minimum to the second,... of the array A*
```
SelectionSort(A):
    for (i = 1,2,...N) do:
        for (j = i,i+1,...N) do:
            key := index of A such that A[key] is minium
        swap(A[i], A[key])
```

3. Insertion Sort

*Idea : This method will divide the array A in to Sorted_Part and Unsorted_Part. For each iteration, InsertionSort will take 1 element from Unsorted_Part and sort with Sorted_Part.*
```
InsertionSort(A):
    for (i = 1,2,3..N) do:
        key := A[i] <the element from Unsorted_Part>
        j = i-1
        while (A[j] > key) and j >= 0:
            A[j+1] = A[j]   // Overwrite to array A
            j = j - 1
        A[j+1] = key   // return the value of A[j+1]
```

4. Merge Sort
```
MergeSort(A):
    if len(A) > 1:
        M = integer(N/2)
        L = A[1,2,...M]
        R = A[M+1,M+2,...N]

        MergeSort(L)
        MergeSort(R)

        /// Merge element
        while (i < |L|) and (j < |R|) do:
            <Take element of both array into index of A>
        
        <if 1 array is DONE then put all the rest of elements in other array to A>
    return A
```

5. Quick Sort
```
QuickSort(A):
    if N <= 1:
        return A
    
    pivot = A[N/2]
    L = [<elements in A less than pivot>]
    R = [<elements in A greater than pivot>]
    M = [<elements in A equal to pivot>]

    return QuickSort(L) + M + QuickSort(R)
```

6. Heap Sort
```
```

7. TOPO Sort
```
```