### [Clone Graph](https://leetcode.com/problems/clone-graph/)


### Problem
Given a reference of a node in a connected undirected graph.

Return a deep copy (clone) of the graph.

Each node in the graph contains a value (int) and a list (List[Node]) of its neighbors.

class Node {
    public int val;
    public List<Node> neighbors;
}
 

Test case format:

For simplicity, each node's value is the same as the node's index (1-indexed). For example, the first node with val == 1, the second node with val == 2, and so on. The graph is represented in the test case using an adjacency list.

An adjacency list is a collection of unordered lists used to represent a finite graph. Each list describes the set of neighbors of a node in the graph.

The given node will always be the first node with val = 1. You must return the copy of the given node as a reference to the cloned graph.

### Idea
Use dfs, Nodes already created are placed in a hash map to prevent them from being created again.

### Solution
While touring each node, it creates a new object and puts it in a hash map.

### Code
Time Complexity : O(n*m) \
Space Complexity : O(n)
```java
class Solution {
    public Node cloneGraph(Node node) {
        if(node == null) return null;
        Map<Integer, Node> map = new HashMap<>();
        return cloneGraph(node, map);
    }
    
    public Node cloneGraph(Node node, Map<Integer, Node> map) {        
        if(map.containsKey(node.val)) {
            return map.get(node.val);
        }
                
        Node newNode = new Node(node.val, new ArrayList<>());
        map.put(newNode.val, newNode);
        
        for(Node n : node.neighbors) {
            newNode.neighbors.add(cloneGraph(n, map));
        }
        
        return newNode;
    } 
}
```

