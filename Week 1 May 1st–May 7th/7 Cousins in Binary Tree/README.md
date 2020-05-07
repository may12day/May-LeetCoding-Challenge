# Solution
```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

# Method 1 : BFS

from collections import deque
class Solution:
    def isCousins(self, root: TreeNode, x: int, y: int) -> bool:
        parent = None
        depth = 0
        stack = deque()
        stack.append((root,parent,depth))
        dic = defaultdict()
        while stack:
            node,parent,depth = stack.popleft()
            dic[node.val] = (parent,depth)
            if node.left:
                stack.append((node.left,node,depth+1))
            if node.right:
                stack.append((node.right,node,depth+1))
        
        return dic[x][0]!=dic[y][0] and dic[x][1]==dic[y][1]
    
# Method 2 : DFS

# class Solution:
#     def isCousins(self, root: TreeNode, x: int, y: int) -> bool:

#         def dfs(node: TreeNode, parent: TreeNode, depth: int):
#             if not node or len(results) == 2:
#                 return
#             else:
#                 if node.val == x or node.val == y:
#                     results.append((parent, depth))
#                 dfs(node.left, node, depth + 1)
#                 dfs(node.right, node, depth + 1)

#         results = []
#         dfs(root, None, 0)

#         return results[0][0] != results[1][0] and results[0][1] == results[1][1]

```
