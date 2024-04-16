# Write a function to perform a breadth-first search on a graph

## Problem Description

Breadth-First Search (BFS) is a graph traversal algorithm that explores all the vertices of a graph in breadth-first order. It starts at a given source vertex and explores all the neighboring vertices at the present depth before moving on to the vertices at the next depth level.

The goal is to write a function that performs a BFS on a graph and returns the visited vertices in the order they were visited.

## Requirements

1. The function should take a graph represented as an adjacency list and a starting vertex as input.
2. The function should return an array of visited vertices in the order they were visited.
3. The function should handle both directed and undirected graphs.
4. The function should handle disconnected graphs and visit all reachable vertices.

## JavaScript Code

Here's a JavaScript implementation of a BFS function:

```javascript
function breadthFirstSearch(graph, startVertex) {
  // Initialize a queue and a visited set
  const queue = [startVertex];
  const visited = new Set([startVertex]);

  // Initialize the result array
  const result = [];

  // Perform the BFS
  while (queue.length > 0) {
    const currentVertex = queue.shift();
    result.push(currentVertex);

    // Visit all the neighbors of the current vertex
    for (const neighbor of graph[currentVertex]) {
      if (!visited.has(neighbor)) {
        visited.add(neighbor);
        queue.push(neighbor);
      }
    }
  }

  return result;
}
```

Here's how the function works:

1. We initialize a queue with the starting vertex and a visited set to keep track of the vertices we've already visited.
2. We also initialize an empty result array to store the visited vertices in the order they were visited.
3. We then enter a loop that continues as long as the queue is not empty.
4. In each iteration of the loop, we dequeue the next vertex from the queue, add it to the result array, and then visit all its neighbors.
5. For each neighbor, we check if it has been visited before. If not, we add it to the visited set and enqueue it.
6. Finally, we return the result array containing the visited vertices in the order they were visited.

You can use this function like this:

```javascript
const graph = {
  A: ['B', 'C'],
  B: ['D', 'E'],
  C: ['F'],
  D: [],
  E: ['F'],
  F: []
};

const visitedVertices = breadthFirstSearch(graph, 'A');
console.log(visitedVertices); // Output: ['A', 'B', 'C', 'D', 'E', 'F']
```

In this example, we define a graph as an adjacency list and call the `breadthFirstSearch` function with the graph and the starting vertex 'A'. The function returns an array of visited vertices in the order they were visited.