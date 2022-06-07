### Listing down the following sliding window based problems which all follow same kind of approach with minor tweaks:

* [322. Coin Change](https://leetcode.com/problems/coin-change/)

* [70. Climbing Stairs](https://leetcode.com/problems/climbing-stairs/)

* [198. House Robber](https://leetcode.com/problems/house-robber/)

* [213. House Robber II](https://leetcode.com/problems/house-robber-ii/)

* [91. Decode Ways](https://leetcode.com/problems/decode-ways/)

* [152. Maximum Product Subarray](https://leetcode.com/problems/maximum-product-subarray/)

* [139. Word Break](https://leetcode.com/problems/word-break/)

* [300. Longest Increasing Subsequence](https://leetcode.com/problems/longest-increasing-subsequence/)

* [416. Partition Equal Subset Sum](https://leetcode.com/problems/partition-equal-subset-sum/)



### Framework

暴力穷举 -> 带备忘录的递归解法 -> dp 数组的迭代解法

一般求最值， 而回溯一般就是暴力穷举，找到所有可行， 没有重复因子

### Code Template

```python3
# 自顶向下递归的动态规划 top down (need memo in this way)
def dp(状态1, 状态2, ...):
    for 选择 in 所有可能的选择:
        # 此时的状态已经因为做了选择而改变
        result = 求最值(result, dp(状态1, 状态2, ...))
    return result

# 自底向上迭代的动态规划 bottom up
# 初始化 base case
dp[0][0][...] = base case
# 进行状态转移
for 状态1 in 状态1的所有取值：
    for 状态2 in 状态2的所有取值：
        for ...
            dp[状态1][状态2][...] = 求最值(选择1，选择2...)
```
