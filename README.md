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
    distances[start_node] = 0, distances[<other_nodes>] = INF
    previous[<all_nodes>] = None
    V = V \ {s}   // unvisited_nodes
    for each `v` in V do:
        distances[v] = ADJ[s,v]
        preveous[v] = s

Step 2: Loop
    while (V is not empty) do:
        current_node = min(<nodes in V have the minimum weight>)
        V = V \ {current_node}

        if (distances[current_node] == INF) then: 
            break   // unvisited_odes are not connected to `start_node`

        for each `v` in V do:
            distances[v] = min(distance[v], distances[current_node] + ADJ[current_node, v])
            previous[v] = current_node
        
        if (current_node == end_node) then:
            break


Step 3: Return
    return (distances[s], previous[s])
```