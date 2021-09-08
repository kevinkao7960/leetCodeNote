230 Kth Smallest Element in a BST

# 230. Kth Smallest Element in a BST

*Link: https://leetcode.com/problems/kth-smallest-element-in-a-bst/*

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def kthSmallest(self, root: Optional[TreeNode], k: int) -> int:
        def traverse(node, root):
            if root is None:
                return    
            traverse(node, root.left)
            node.append(root.val)
            traverse(node, root.right)
            
        node = []
        traverse(node, root)
        
        return node[k-1]
```

### Explanation:

The description mentioned that the data structure is a BST.

We can use in-order traverse to get the sorted node value.

In python, the array can be modified in the callee function.

1. Traverse the left node

2. Append the node value into "node" array

3. Traverse the right node

After traverse the whole BST, we would get the node array with sorted numbers already.
Then we just return the value of node[k-1] as the answer.

