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

Step 2: Sort 

Step 3: Loop

Step 4: Return
```

## Breath First Search

```

```

## Depth First Search

```
DFS(u):
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