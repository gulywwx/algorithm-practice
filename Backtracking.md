### Listing down the following sliding window based problems which all follow same kind of approach with minor tweaks:

* [46. Permutations](https://leetcode.com/problems/permutations/)

* [51. N-Queens](https://leetcode.com/problems/n-queens/)


### Framework

* 暴力穷举
* 穷举过程就是遍历多叉树过程
* 代码框架和多叉树遍历类似

### Code Template

```python3
#backtracking framework
result = []
def backtrack(路径, 选择列表):
    if 满足结束条件:
        result.add(路径)
        return
    
    for 选择 in 选择列表:
        做选择
        backtrack(路径, 选择列表)
        撤销选择
        
##multi branch tree
def traverse(root):
  if not root:
    return
    
  for child in root.children:
      traverse(child)
```

### DFS VS Backtrack


```python3
// DFS 算法，关注点在节点
void traverse(TreeNode root) {
    if (root == null) return;
    printf("进入节点 %s", root);
    for (TreeNode child : root.children) {
        traverse(child);
    }
    printf("离开节点 %s", root);
}

// 回溯算法，关注点在树枝
void backtrack(TreeNode root) {
    if (root == null) return;
    for (TreeNode child : root.children) {
        // 做选择
        printf("从 %s 到 %s", root, child);
        backtrack(child);
        // 撤销选择
        printf("从 %s 到 %s", child, root);
    }
}
```


