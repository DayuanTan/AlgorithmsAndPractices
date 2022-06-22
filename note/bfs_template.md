#  BFS Template

- Queue is used to record which nodes need to be process
- Hashtable to record visited nodes if necessary:
  - to avoid repeated calculation
  - to prune in tree 
  - to avlid cycle in graph
  - Java: HashMap/HashSet
  - Python: dict/set
  - C++: unordered_map/unordered_set

这个模版最简洁 分不分层都可以用 

python

```py
# step 1 initialization
# 把初始节点放入deque，如果有多个就都放进去
# 并标记初始节点距离为0（不同题目这里操作不一样）记录下distance的dict里
# distance有2个作用，一是记录已经访问的点，二是记录节点距离
queue = collections.deque([node1, node2 ...])
distance = {node1: 0; node2: 0; ...}

# step 2 iterate the queue
# while-loop then 每次pop queue中的一个点出来接受处理
while queue:
    node = queue.popleft()
    # step 3 extend to next level 扩展相邻节点
    # 找到当前节点的相邻节点，并加入queue并在distance中存储距离
    for neighbor in node.getneighbors():
        if neighbor in distance: # already visited
            continue 
        queue.append(neighbor)
        distance[neighbor] = distance[node] + 1
```

java
```java
Deque<Node> queue = new ArrayDeque<Node>();
HashMap<Node, Integer> distance = new HashMap<>();

queue.offer(node);
distance.put(node, 0);

while (!queue.isEmpty()){
    Node node = queue.poll();
    for (Node neighbor: node.getneighbors()){
        if (distance.containsKey(neighbor)){
            continue;
        }
        queue.offer(neighbor);
        distance.put(neighbor, distance.get(node) + 1);
    }
}
```


# 分层 VS 不分层

有些问题要求分层， 比如102 解法1

## 不分层

```py
def find_nodes_by_bfs(self, node):
    queue = collections.deque([node])
    visited = set([node])
    while queue:
        curr_node = queue.popleft()
        for neighbor in curr_node.neighbors():
            if nieghbor in visited:
                continue
            visited.add(neighbor)
            queue.append(neighbor)
    return list(visited)
```


## 分层 （仅一行区别）
```py
def find_nodes_by_bfs(self, node):
    queue = collections.deque([node])
    visited = set([node])
    while queue:
        for _ in range(len(queue)): # 仅一行区别
            curr_node = queue.popleft()
            for neighbor in curr_node.neighbors():
                if nieghbor in visited:
                    continue
                visited.add(neighbor)
                queue.append(neighbor)
    return list(visited)
```


# Bi-BFS 双向宽度优先搜索代码模板

```
初始化forward_quque forward_set , 加入起点
初始化backward_quque backward_set , 加入起点
distance = 0

while forward_quque backward_quque 都非空：
    distance += 1
    for all nodes in forward_queue:
        扩展出下一层的点放入forward_queue 和forward_set里面
        if 碰到了backward_set里面的点：
            return distance
    
    distance += 1
    for all nodes in backward_queue:
        扩展出下一层的点放入backward_queue 和backward_set里面
        if 碰到了forward_set里面的点：
            return distance
return not found
```