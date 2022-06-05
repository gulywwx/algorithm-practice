### Listing down the following sliding window based problems which all follow same kind of approach with minor tweaks:

* [46. Permutations](https://leetcode.com/problems/permutations/)

* [N-Queens](https://leetcode.com/problems/n-queens/)


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
        
##backtracking framework
def traverse(root):
  if not root:
    return
    
  for child in root.children:
      traverse(child)
```
