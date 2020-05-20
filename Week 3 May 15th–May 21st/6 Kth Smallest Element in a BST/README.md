# Solution
```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

# Method 1
class Solution:
    def kthSmallest(self, root: TreeNode, k: int) -> int:
        arr = []
        
        def dfs(node):
            if node is None or len(arr)>k :
                return
            
            dfs(node.left)
            arr.append(node.val)
            dfs(node.right)
        
        dfs(root)
        return arr[k-1]


# Method 2
class Solution:
    def kthSmallest(self, root: TreeNode, k: int) -> int:
        self.count = 0
        def inorder(root):
            if not root:
                return 
            inorder(root.left)
            self.count += 1
            if self.count == k:
                self.res = root.val
                return
            inorder(root.right)
        
        inorder(root)
        return self.res
        
```
