### Listing down the following sliding window based problems which all follow same kind of approach with minor tweaks:

* [3.Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

* [76.Minimum Window Substring](https://leetcode.com/problems/minimum-window-substring/)

* [438.Find All Anagrams in a String](https://leetcode.com/problems/find-all-anagrams-in-a-string/)

* [567.Permutation in String](https://leetcode.com/problems/permutation-in-string/)

* [424. Longest Repeating Character Replacement](https://leetcode.com/problems/longest-repeating-character-replacement/)

### Basic template of such problems is basically 3 steps.

* Step1: Have a counter or hash-map to count specific array input and keep on increasing the window toward right using outer loop.

* Step2: Have a while loop inside to reduce the window side by sliding toward right. Movement will be based on constraints of problem. Go through few examples below

* Step3: Store the current maximum window size or minimum window size or number of windows based on problem requirement.

### Code Template

```python3
def slidingWindow(s:str,t:str):
    '''初始化 window 和 need 两个哈希表，记录窗口中的字符和需要凑齐的字符：'''
    need, window = collections.defaultdict(int), collections.defaultdict(int) # {char:int}
    for c in t:
        need[c] += 1
    left, right = 0, 0
    valid = 0 # 表示窗口中满足need条件的字符个数，如果valid和len(need)的大小相同，则说明窗口已满足条件
    '''使用 left 和 right 变量初始化窗口的两端，不要忘了，区间 [left, right) 是左闭右开的，所以初始情况下窗口没有包含任何元素：'''
    while right < len(s):
        # c是将要移入窗口的字符
        c = s[right]
        # 增大窗口
        right += 1
        # 进行窗口内数据的一系列更新
        ..."""更新窗口数据的地方"""

        # 判断左侧窗口是否要收缩
        while '''window needs shrink''':
            # d是将要移出窗口的字符
            d = s[left]
            # 缩小窗口
            left += 1
            # 进行窗口内数据的一系列更新
        	..."""更新窗口数据的地方"""
```
