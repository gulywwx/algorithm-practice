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

### 形式一 元素无重不可复选，即 nums 中的元素都是唯一的，每个元素最多只能被使用一次

```python3

# 组合/子集问题回溯算法框架
def backtrack(nums: List[int], start: int):
    # 回溯算法标准框架
    for i in range(start,len(nums)):
        // 做选择
        track.append(nums[i])
        // 注意参数
        backtrack(nums, i + 1)
        // 撤销选择
        track.pop()
        

# 排列问题回溯算法框架
def backtrack(nums: List[int]):
    for i in range(len(nums)):
        # 剪枝逻辑
        if used[i]:
            continue
        # 做选择
        used[i] = True;
        track.append(nums[i])

        backtrack(nums)
        # 撤销选择
        track.pop()
        used[i] = False
        
```

### 形式二 元素可重不可复选，即 nums 中的元素可以存在重复，每个元素最多只能被使用一次，其关键在于排序和剪枝

```python3

# 组合/子集问题回溯算法框架
# 40. Combination Sum II
nums.sort()
def backtrack(nums: List[int], start: int):
    # 回溯算法标准框架
    for i in range(start,len(nums)):
        # 剪枝逻辑，跳过值相同的相邻树枝
        if i > start and nums[i] == nums[i - 1]:
            continue
        # 做选择
        track.append(nums[i])
        # 注意参数
        backtrack(nums, i + 1)
        # 撤销选择
        track.pop()           


# 排列问题回溯算法框架
nums.sort()
def backtrack(nums: List[int]):
    for i in range(len(nums)):
        # 剪枝逻辑
        if used[i]:
            continue
        # 剪枝逻辑，固定相同的元素在排列中的相对位置
        if i > 0 and nums[i] == nums[i - 1] and not used[i - 1]:
            continue
        # 做选择
        used[i] = True
        track.append(nums[i])

        backtrack(nums)
        # 撤销选择
        track.pop()
        used[i] = False
        
```

### 形式三 元素无重可复选，即 nums 中的元素都是唯一的，每个元素可以被使用若干次，只要删掉去重逻辑即可

```python3
# 组合/子集问题回溯算法框架
def backtrack(nums: List[int], start: int):
    # 回溯算法标准框架
    for i in range(start,len(nums)):
        # 做选择
        track.append(nums[i])
        # 注意参数
        backtrack(nums, i)
        # 撤销选择
        track.pop()


# 排列问题回溯算法框架
def backtrack(nums: List[int]):
    for i in range(len(nums)):
        # 做选择
        track.append(nums[i])
        backtrack(nums)
        # 撤销选择
        track.pop()
```

