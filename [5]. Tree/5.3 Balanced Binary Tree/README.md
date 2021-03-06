# Balanced Binary Tree (平衡二叉树)



## From



[LeetCode 110](https://leetcode-cn.com/problems/balanced-binary-tree/)





## Question

Given a binary tree, determine if it is height-balanced.

For this problem, a height-balanced binary tree is defined as:

> a binary tree in which the depth of the two subtrees of *every* node never differ by more than 1.

**Example 1:**

Given the following tree `[3,9,20,null,null,15,7]`:

```
    3
   / \
  9  20
    /  \
   15   7
```

Return true.
**Example 2:**

Given the following tree `[1,2,2,3,3,null,null,4,4]`:

```
       1
      / \
     2   2
    / \
   3   3
  / \
 4   4

```

Return false.



## Solution  



### Python3

```python3
class Solution:
    def isBalanced(self, root):
        """
        :type root: TreeNode
        :rtype: bool
        """
        return self.balancedHeight(root) >= 0
    def balancedHeight(self, root):
        if root is None:
            return 0    # 终止条件
        left = self.balancedHeight(root.left)
        right = self.balancedHeight(root.right)
        if left < 0 or right < 0 or abs(left - right) > 1:
            return -1   # 终止条件
        return max(left, right) + 1
```

