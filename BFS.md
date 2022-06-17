### Listing down the following sliding window based problems which all follow same kind of approach with minor tweaks:

* [111. Minimum Depth of Binary Tree](https://leetcode.com/problems/minimum-depth-of-binary-tree/)

* [752. Open the Lock](https://leetcode.com/problems/open-the-lock/)


### Framework

* BFS 找到的路径一定是最短的，但代价就是空间复杂度可能比 DFS 大很多
* 问题的本质就是让你在一幅「图」中找到从起点 start 到终点 target 的最近距离
* 用队列实现

### Code Template

```python3
def BFS(start: TreeNode, target: TreeNode) -> int:
    # 核心数据结构
    queue = deque([])
    # 避免走回头路
    visited = set()

    # 将起点加入队列
    queue.append(start)
    visited.add(start)

    # 记录扩散的步数
    step = 0

    # 当队列不为空
    while queue:
        # 当前层的节点数
        n = len(queue)
        # 将当前队列中的所有节点向四周扩散
        for i in range(n):    
            cur = queue.q.popleft()
            # 划重点：这里判断是否到达终点
            if cur is target:
                return step
            #  将 cur 的相邻节点加入队列   
            if cur.left:
                if cur not in visited:
                    queue.append(cur.left)
                    visited.add(cur)
            if cur.right:
                if cur not in visited:            
                    queue.append(cur.right)   
                    visited.add(cur)
        # 划重点：更新步数在这里            
        step += 1
```
