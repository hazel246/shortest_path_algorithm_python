# Shortest Path Finder

This project is part of the **Scientific Computing with Python** curriculum from **freeCodeCamp.**<br>
This project implements a **shortest path algorithm** (similar to Dijkstra's algorithm) to find the shortest distances and paths in a weighted graph.


## Features

- **Input:**
  - A weighted graph represented as an adjacency list.
  - A starting node.
  - An optional target node.
- **Output:**
  - The shortest distances from the starting node to all other nodes.
  - The shortest path from the starting node to each node.
  - If a target node is specified, only the distance and path to that target are printed.
 
# Requirements
Python 3.6 or higher.
## Usage
Define your graph as an adjacency list.
Call shortest_path(graph, start) to calculate the shortest paths and distances.

## Graph Representation

The graph is represented as an adjacency list in Python:


```python
my_graph = {
    'A': [('B', 5), ('C', 3), ('E', 11)],
    'B': [('A', 5), ('C', 1), ('F', 2)],
    'C': [('A', 3), ('B', 1), ('D', 1), ('E', 5)],
    'D': [('C', 1), ('E', 9), ('F', 3)],
    'E': [('A', 11), ('C', 5), ('D', 9)],
    'F': [('B', 2), ('D', 3)]
}
How It Works
Initialization:

Distances: The distance to the starting node is set to 0, and all other nodes are set to infinity (∞).
Paths: Tracks the shortest path to each node. The starting node path contains itself initially.
Unvisited Nodes: All nodes are added to an unvisited list.
Algorithm Steps:

Select the unvisited node with the smallest current distance.
For each neighbor of the selected node:
If a shorter distance to the neighbor is found, update the neighbor's distance.
Update the path to include the new shortest route.
Remove the selected node from the unvisited list.
Output:

Prints the shortest distance and path from the starting node to:
All nodes, if no target is specified.
A specific target node, if provided.
Example Output
For the following graph and starting node 'A':

python

my_graph = {
    'A': [('B', 5), ('C', 3), ('E', 11)],
    'B': [('A', 5), ('C', 1), ('F', 2)],
    'C': [('A', 3), ('B', 1), ('D', 1), ('E', 5)],
    'D': [('C', 1), ('E', 9), ('F', 3)],
    'E': [('A', 11), ('C', 5), ('D', 9)],
    'F': [('B', 2), ('D', 3)]
}
shortest_path(my_graph, 'A')
The output will be:

A-B distance: 5
Path: A -> B

A-C distance: 3
Path: A -> C

A-D distance: 4
Path: A -> C -> D

A-E distance: 8
Path: A -> C -> E

A-F distance: 7
Path: A -> B -> F




