# Ex23 Breadth-First Search (BFS) Traversal of a City Junction Map
## DATE: 03-09-2026
## AIM:
To design and implement a java program to perform Breadth-First Search (BFS) traversal on a city’s junction map represented as a graph, and find all reachable locations from a given source junction.
## Algorithm
1. Start the program.
2. Represent the city junction map as a graph using an adjacency list (dictionary).
3. Define a function bfs(graph, start) that performs Breadth-First Search traversal:
4. Initialize a queue and a list to keep track of visited junctions.
5. Enqueue the starting junction.
6. While the queue is not empty:
7. Dequeue a junction and mark it as visited.
8. Print or store the junction in traversal order.
9. In the main section:
10. Define the city map as a graph (each node represents a junction).
11. Take a starting junction as input (or use a fixed source).
12. Call the bfs() function to display reachable locations.
13. Stop the program.  

## Program:
```java
/*
Program to perform Breadth-First Search (BFS) traversal on a city’s junction map represented as a graph
Developed by:Syed  Mohamed Raihan M
RegisterNumber:  212223040167
*/

import java.util.*;

public class EmergencyRouteBFS {
    public static void addEdge(List<List<Integer>> g, int u, int v) {
        g.get(u).add(v);
        g.get(v).add(u);
    }

    public static void bfs(List<List<Integer>> g, int src, boolean[] visited) {
        Queue<Integer> q = new LinkedList<>();
        q.offer(src);
        visited[src] = true;
        while (!q.isEmpty()) {
            int curr = q.poll();
            System.out.print(curr + " ");
            for (int neighbor : g.get(curr)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    q.offer(neighbor);
                }
            }
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(), e = sc.nextInt();
        List<List<Integer>> g = new ArrayList<>();
        for (int i = 0; i < n; i++) g.add(new ArrayList<>());
        for (int i = 0; i < e; i++) addEdge(g, sc.nextInt(), sc.nextInt());
        int src = sc.nextInt();
        bfs(g, src, new boolean[n]);
    }
}
```

## Output:
<img width="332" height="209" alt="image" src="https://github.com/user-attachments/assets/a38cd297-cc39-4eb9-b35e-0d8396223e21" />



## Result:
The program has been successfully implemented and executed.
It performs Breadth-First Search (BFS) traversal on a city junction map and correctly lists all reachable locations from the given source node.
