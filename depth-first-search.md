## DFS
A depth first search algorithm is a search majorly used in graph and trees, we can start seraching from any node (say it root node) and go deep down along the path, backtrack if not found and the seraching continues until we found the that node.

In dfs we select one child and traverse the complete child tree before moving to next child of the node.<br />
**Note**** Traversing only non visited node (if current node is already been visited then move to next node since we must had done dfs on that node so no need to traverse again). 

### Sequence diagram
```
step 1 -> if current_node is already been visited then just return otherwise traverse over the childrens of current_node->childs
step 2 -> do dfs one-by-one on each child
```
![tree_sequence_diagram](https://user-images.githubusercontent.com/35250507/180637909-79cedb37-aec9-4ae0-b730-3e62bf054bf2.png)

### Example
let's say we have a tree of 8 nodes, where node 1 is the root.
![tree](https://user-images.githubusercontent.com/35250507/180635107-3de1a9ef-a212-4347-af39-3c02622e89f2.png)

Now we want to search a node with a value as 8 using dfs (depth first search), start with the root node


https://user-images.githubusercontent.com/35250507/180635263-f90e9a75-0f2b-4501-b31b-7c50d83ce713.mp4

### sudo code
- I always use `vector <vector <int>> node(N)` for nodes, node[i] stores the list of children nodes of for ith node, you are free to use anything 🙂.

```
void dfs(int current_node, int parrent) {
  for (int child : node[current_node]) {
    if (child == parrent) {
      return ;
    }
    dfs(child, current_node);
  }
}
```
