#  BFS Template

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
        if neighbor not in distance: # already visited
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