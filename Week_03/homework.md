#### 236. 二叉树的最近公共祖先
[leetcode#236-lowestCommonAncestor](https://leetcode-cn.com/problems/lowest-common-ancestor-of-a-binary-tree/)

```python
class Solution:
    def lowestCommonAncestor(self, root: 'TreeNode', p: 'TreeNode', q: 'TreeNode') -> 'TreeNode':
        if not root or root == p or root == q: 
            return root
        left = self.lowestCommonAncestor(root.left,p,q)
        right = self.lowestCommonAncestor(root.right,p,q)

        if not left:
            return right
        if not right:
            return left
        return root
```

[参考Krahets的题解](https://leetcode-cn.com/problems/lowest-common-ancestor-of-a-binary-tree/solution/236-er-cha-shu-de-zui-jin-gong-gong-zu-xian-hou-xu/)


#### 46. 全排列
[leetcode#46-premute](https://leetcode-cn.com/problems/permutations/)

```python
class Solution:
    def permute(self, nums: List[int]) -> List[List[int]]:
        res = []
        def backtrack(nums, tmp_lst):
            if not nums:
                res.append(tmp_lst)
                return
            for i in range(len(nums)):
                backtrack(nums[:i]+nums[i+1:], tmp_lst+[nums[i]])
        
        backtrack(nums,[])
        return res
```

[参考powcai的题解](https://leetcode-cn.com/problems/permutations/solution/hui-su-suan-fa-by-powcai-2/)