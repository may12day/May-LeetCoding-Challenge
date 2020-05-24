# Solution
```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

# Method 1 : Iterative O(n)
# class Solution:
    def bstFromPreorder(self, preorder: List[int]) -> TreeNode:
        root = TreeNode(preorder[0])
        stack = [root]
        for value in preorder[1:]:
            if value < stack[-1].val:
                stack[-1].left = TreeNode(value)
                stack.append(stack[-1].left)
            else:
                while stack and stack[-1].val < value:
                    last = stack.pop()
                last.right = TreeNode(value)
                stack.append(last.right)
        return root
    
# Method 2 : Recursive O(nlogn)
class Solution:
    def bstFromPreorder(self, preorder: List[int]) -> TreeNode:
        if not preorder: return None
        
        node = TreeNode(preorder.pop(0))
        
        index = len(preorder)
        for i, val in enumerate(preorder):
            if val > node.val:
                index = i
                break
                
        node.left = self.bstFromPreorder(preorder[:index])
        node.right = self.bstFromPreorder(preorder[index:])
        
        return node
        
```
