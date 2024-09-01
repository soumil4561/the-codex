## Base Approach
BFS Traversal. Using adjacency matrix and queue. Keep a distance array for keeping track of distance for each node from src with dist[src] = 0 and dist[everyone else] = Int_MAX_VAL
`Distance is updated if distance[node]+weight<distance[neighbours]`

if distance of any element = Int_MAX_VAL dist[i] = -1

### Code
```java
public int[] shortestPath(int[][] edges,int n,int m ,int src) {
        // Code here
        ArrayList<ArrayList<Integer>> graph = new ArrayList<>();
        for(int i=0;i<n;i++) graph.add(new ArrayList<>());
        for(int[] edge:edges){
            graph.get(edge[0]).add(edge[1]);
            graph.get(edge[1]).add(edge[0]);
        }
        // for(int i=0;i<n;i++) System.out.println(graph.get(i));
        int[] distance = new int[n];
        for(int i = 0;i<n;i++) distance[i] = 10000000;
        Queue<Integer> queue = new LinkedList<>();
        queue.add(src);
        distance[src] = 0;
        while(!queue.isEmpty()){
            int node = queue.remove();
            for(Integer neighbours: graph.get(node)){
                if(distance[node]+1<distance[neighbours]){
                    queue.add(neighbours);
                    distance[neighbours] = 1+distance[node];
                }
            }
        }
        
        for(int i=0;i<n;i++){
            if(distance[i]==10000000) distance[i] = -1;
        }
        return distance;
    }
```

## Dijsktra's Algorithm
Also BFS, but instead of queue, use PriorityQueue, as the lower weight edges will come out first, and update distance array faster. Basically 'base approach' with sorting the edge weights

"Does not work well with negative weights"
'Reason to be updated'

