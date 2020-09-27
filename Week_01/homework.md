
#### 26. 删除数组的重复项
[leetcode#26-removeDuplicates](https://leetcode-cn.com/problems/remove-duplicates-from-sorted-array/)

```python
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        a=0
        b=0
        while b < len(nums):
            if nums[a] == nums[b]:
                b += 1
            elif nums[a] != nums[b]:
                nums[a+1] = nums[b]
                a += 1
        return a+1
```
- 思路: 双指针。
    - 重复的时候，快指针往前跳；不重复的时候，慢指针往前。

#### 21. 合并两个有序链表
[leetcode#21-mergeTwoLists](https://leetcode-cn.com/problems/merge-two-sorted-lists/)

```python
class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
        if l1 is None:
            return l2
        elif l2 is None:
            return l1
        elif l1.val < l2.val:
            l1.next = self.mergeTwoLists(l1.next, l2)
            return l1
        else:
            l2.next = self.mergeTwoLists(l1, l2.next)
            return l2
```

- 思路:递归

#### 1. 两数之和
[leetcode#1-twoSum](https://leetcode-cn.com/problems/two-sum/)
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        hashmap = {}

        # 把数据存进hashmap
        for ind, num in enumerate(nums):
            hashmap[num] = ind
        
        # 遍历数据
        for i,num in enumerate(nums):
            j = hashmap.get(target-num)
            if j is not None and i != j:
                return [i,j]
```
- 思路: 字典模拟哈希求解过程

#### 66. 加一
[leetcode#66-plusOne](https://leetcode-cn.com/problems/plus-one/)
```python
class Solution:
    def plusOne(self, digits: List[int]) -> List[int]:
        # 变为实际数字
        num = 0
        for i in range(len(digits)):
            num += (10**i) * digits[len(digits)-1-i]
        # 数字加一
        result_num = num + 1
        result_list = []
        # 转变为list
        for i in range(len(str(result_num))):
            result_list.append(int(str(result_num)[i]))
        return result_list
```
- 思路: 暴力法，先转变成数字，加一后，转换回list

