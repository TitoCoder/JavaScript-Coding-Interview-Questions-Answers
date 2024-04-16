# Write a function to implement a graph data structure

## Graph Data Structure

### Problem Description

A graph is a data structure that consists of a set of vertices (or nodes) and a set of edges that connect these vertices. Graphs are used to represent relationships between objects or entities, and they have a wide range of applications in computer science, social networks, transportation systems, and many other domains.

Implementing a graph data structure in JavaScript can be a useful skill to have, as it allows you to work with and manipulate complex data structures and solve problems that involve relationships between entities.

### Requirements

Implement a `Graph` class in JavaScript that supports the following operations:

1. **Add Vertex**: Add a new vertex to the graph.
2. **Add Edge**: Add an edge between two vertices in the graph.
3. **Remove Vertex**: Remove a vertex from the graph.
4. **Remove Edge**: Remove an edge between two vertices in the graph.
5. **Traverse Graph**: Implement a method to traverse the graph, such as depth-first search (DFS) or breadth-first search (BFS).

The `Graph` class should have the following properties:

- `vertices`: an array or object to store the vertices in the graph.
- `edges`: an array or object to store the edges in the graph.

### JavaScript Code

Here's an example implementation of a `Graph` class in JavaScript that meets the requirements:

```javascript
class Graph {
  constructor() {
    this.vertices = {};
    this.edges = {};
  }

  addVertex(vertex) {
    this.vertices[vertex] = [];
  }

  addEdge(vertex1, vertex2) {
    if (!this.vertices[vertex1]) {
      this.addVertex(vertex1);
    }
    if (!this.vertices[vertex2]) {
      this.addVertex(vertex2);
    }
    this.vertices[vertex1].push(vertex2);
    this.vertices[vertex2].push(vertex1);
    this.edges[`${vertex1}-${vertex2}`] = true;
  }

  removeVertex(vertex) {
    if (!this.vertices[vertex]) return;
    for (let neighbor of this.vertices[vertex]) {
      this.removeEdge(vertex, neighbor);
    }
    delete this.vertices[vertex];
  }

  removeEdge(vertex1, vertex2) {
    if (this.edges[`${vertex1}-${vertex2}`]) {
      this.vertices[vertex1] = this.vertices[vertex1].filter(v => v !== vertex2);
      this.vertices[vertex2] = this.vertices[vertex2].filter(v => v !== vertex1);
      delete this.edges[`${vertex1}-${vertex2}`];
    }
  }

  depthFirstSearch(startVertex, callback) {
    const visited = {};
    const stack = [startVertex];

    while (stack.length > 0) {
      const currentVertex = stack.pop();
      if (!visited[currentVertex]) {
        visited[currentVertex] = true;
        callback(currentVertex);
        for (let neighbor of this.vertices[currentVertex]) {
          stack.push(neighbor);
        }
      }
    }
  }

  breadthFirstSearch(startVertex, callback) {
    const visited = {};
    const queue = [startVertex];

    while (queue.length > 0) {
      const currentVertex = queue.shift();
      if (!visited[currentVertex]) {
        visited[currentVertex] = true;
        callback(currentVertex);
        for (let neighbor of this.vertices[currentVertex]) {
          queue.push(neighbor);
        }
      }
    }
  }
}
```

This implementation provides the required functionality for a graph data structure in JavaScript, including methods for adding and removing vertices and edges, as well as depth-first and breadth-first search algorithms for traversing the graph.

You can use this `Graph` class to create and manipulate graph-based data structures in your JavaScript applications.