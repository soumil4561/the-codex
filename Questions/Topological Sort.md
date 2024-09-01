Topological sorting for *Directed Acyclic Graph (DAG)* is a linear ordering of vertices such that for every directed edge u-v, vertex *u* comes before *v* in the ordering.
Topological sorting is a dependency problem in which completion of one task depends upon the completion of several other tasks whose order can vary.
**Algorithm**
- Create a graph with **n** vertices and **m**-directed edges.
- Initialize a stack and a visited array of size **n**.
- For each unvisited vertex in the graph, do the following:
    - Call the DFS function with the vertex as the parameter.
    - In the DFS function, mark the vertex as visited and recursively call the DFS function for all unvisited neighbors of the vertex.
    - Once all the neighbors have been visited, push the vertex onto the stack.
- After all, vertices have been visited, pop elements from the stack and append them to the output list until the stack is empty.
- The resulting list is the topologically sorted order of the graph.

## Code
```java
public String TopologicalSort(ArrayList<ArrayList<Integer>> graph){

        // graph is adjacency list

        // Empty stack also given

        Stack<Integer> stack = new Stack<>();

        for(int i=0;i<visited.length;i++){

            if(!visited[i]) dfs(graph,stack,i);

        }

        StringBuilder sb = new StringBuilder();

        while(!stack.isEmpty()) sb.append(stack.pop());

        return sb.toString();

    }

  

    public void dfs(ArrayList<ArrayList<Integer>> graph, Stack<Integer> stack, int i){

        visited[i] = true;

        for(int node: graph.get(i)){

            if(!visited[node]) dfs(graph,stack,node);

        }

        stack.push(i);

        return;

    }
```

### How to detect cycles using this:
Simply traverse the way we do. If the neighbour is already visited then it means that there is a cycle and return true;
