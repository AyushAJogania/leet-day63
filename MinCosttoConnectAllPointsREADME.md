# leet-day63

# Minimum Cost to Connect All Points

## Problem Description

You are given an array `points` representing integer coordinates of some points on a 2D-plane, where `points[i] = [xi, yi]`.

The cost of connecting two points `[xi, yi]` and `[xj, yj]` is the Manhattan distance between them: `|xi - xj| + |yi - yj|`, where `|val|` denotes the absolute value of `val`.

Return the minimum cost to make all points connected. All points are connected if there is exactly one simple path between any two points.

## Example

Input:

```
points = [[0,0],[2,2],[3,10],[5,2],[7,0]]
```

Output:

```
20
```

Explanation:

We can connect the points as shown above to get the minimum cost of 20. Notice that there is a unique path between every pair of points.

## Constraints

- `1 <= points.length <= 1000`
- `-10^6 <= xi, yi <= 10^6`
- All pairs `(xi, yi)` are distinct.

## Approach

To solve this problem, we can follow these steps:

1. Create a weighted graph where each point is a node, and the weight of an edge between two nodes is the Manhattan distance between their coordinates.

2. Use Kruskal's algorithm to find the minimum spanning tree (MST) of the graph. Kruskal's algorithm is an efficient way to find the MST of a graph.

3. Calculate the total weight of the MST, which represents the minimum cost to connect all points.

## Complexity Analysis

The time complexity for this approach is O(n^2 * log(n)) due to sorting of edges, where n is the number of points. The space complexity is O(n^2) to store the edges.
