# How to Solve - Graphs

## What is a Graph?

A **Graph** ia a collection of nodes or values called __vertices__ that might be related. This **relation** between vertices is called **edges**.

Look at the image below:

![Graph Example](./img/g-1.png)


If we convert this Graph into code it should look like this:

```c++
int main()
{
  int graph[5][5] = {
    {0, 2, 0, 0, 3}, // 0
    {2, 0, 2, 2, 4}, // 1
    {0, 2, 0, 5, 0}, // 2
    {0, 2, 5, 0, 1}, // 3
    {3, 4, 0, 1, 0}  // 4
  };
}
```

Yeah, I know, you must be wondering what is that matrix. See the comments in the code, each row corresponds to a vertice.

Now look at vertice 0, it is connected to vertice 1 and vertice 4. If we look at the row we have the following:

```c++
 { V0, V1, V2, V3, V4 },
 { 0,  2,  0,  0,  3  }
```

Now you can see that each value of the row corresponds to the edge with each vertice. Vertice 0 is only connected with Vertice 1 and 4, the value that we use is the **weight of the edge**.

If you think that the vertices are Stores, and the edges are the distance between them, then you can look for the shortest way for reaching Vertice 2 starting from Vertice 0. The Answer is 4, using V0 -> V1 -> V2.

Obviously with this you can also get the longest route: V0 -> V4 -> V2 -> V3 -> V5.

This is also known as **weight adjacency matrix**, there is another type of matrix called **contact matrix** the main diference is that this matrix only indicates connection.

So our graph would look like this:

```c++
int main()
{
  int graph[5][5] = {
    {0, 1, 0, 0, 1},
    {1, 0, 1, 1, 1},
    {0, 1, 0, 1, 0},
    {0, 1, 1, 0, 1},
    {1, 1, 0, 1, 0}
  };
}
```

Ok, we have desviated from the main topic, so let's continue explaining about the graphs. Until now I have give you the main elements of a graph, but not all of them.

There are two types of graphs those who are connected and those who are disconnected. Look the following image to understand the main difference between them:

![Graph Conn Disconn](./img/g-2.png);

Yes, as you can see a graph is disconnected if part of the graph is unreachable. As you can see nodes 1, 2 and 3 cannot reach by any mean to nodes 4 and 5, and viceversa nodes 4 and 5 cannot reach nodes 1, 2 and 3.

Keep in mind this since this could be a mind break when you are looking to resolve an issue using graphs.

Also, did you notice? Why did I use arrows in the previous image, but in the first image I didn't use them, well this is because the graph connections could be unidirectional or bidirectional. 

In the previous image you see that you can reach from node 1 the nodes 2 and 3, but you cannot reach node 1 from node 3.

![Graph unreachable](./img/g-3.png)

Obviously this can be possible if the nodes 1 and 3 where connected in a bidirectional way.

![Graph bidirectional](./img/g-4.png)

**NOTE**: We are calling Bidirectional or Unidirectional but in reality, the correct name is Undirected Graph and Directed Graph.

![Graph Undirected and Directed](./img/g-4.2.png)

Also keep aware of cyclic graphs, yeah don't be horrorized they are very common, and is something that you must keep aware when you are programming solutions like DFS (Deep First Search) or BFS (Breadth First Search).


Well let's review some of this. What is a Cyclic Graph?, a Cyclic Graph is when the connections lead to a node that is already visited. Let's see the following image:

![Graph Cyclic](./img/g-5.png)

With this you can see that we had some pseudo algorithm to visit all the nodes by only checking their adjacencies, but what is happening if that when there is a cycle on the graph our algorithm is stuck. This will lead to an Memory Error since we will be infinitely iterating nodes 3, 4 and 5.

## How to Initialize a Graph

Yeah we defined how a graph should like into code, in the hardcoded way, but you must remember, you cannot create a dynamic matrix, so we need at first know our vertices.

The simplest thing to do is ask how many vertices we have.

```c++
  int n;

  scanf("%d", &n);
```

The next step is to create our graph:

```c++
#include <iostream>
#include <cstring>

using namespace std;

int main() {
  // How many vertices?
  int n = 5;

  int graph[n][n]; // A matrix 5x5
  char str[100];

  // For each row
  for (int i = 0; i < n; i++) {
    cout << " Enter edges for row " << i << endl;
    cin.getline(str, 100);
    // Ex: 1,0,0,1,0

    int j = 0;
    char *ptr; 
    ptr = strtok(str, " , ");

    // Add edge values to the graph
    while (ptr != NULL) {
      // Convert to integer.
      sscanf(ptr, "%d", &graph[i][j]);

      j++;
      ptr = strtok(NULL, " , ");
    }
  }
}
```

With all this now you have a graph representation. So you can start working on some Algorithms.

### Dijkstra

We will start defining **Greedy Algorithm** is a simple, intuitive algorithm that is used in optimization problems. The algorithm tries to find the overall optimal way to solve the problem.

https://www.geeksforgeeks.org/dijkstras-shortest-path-algorithm-greedy-algo-7/