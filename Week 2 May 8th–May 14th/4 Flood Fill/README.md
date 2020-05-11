# Solution
```
Method 1 : BFS
from collections import deque
class Solution:
    def floodFill(self, image: List[List[int]], sr: int, sc: int, newColor: int) -> List[List[int]]:
        rows = len(image)
        cols = len(image[0])
        directions = [(0,1),(1,0),(-1,0),(0,-1)]
        
        def bfs(row,col,oldColor):
            q = deque()
            q.append((row,col))
            while q:
                x1,y1 = q.popleft()
                for dx,dy in directions:
                    x = x1+dx
                    y = y1+dy
                    if x<rows and x>=0 and y<cols and y>=0 and image[x][y]==oldColor:
                        image[x][y]=newColor
                        q.append((x,y))
                        
        
        if image[sr][sc]==newColor:
            return image
        else:
            oldColor = image[sr][sc]
            image[sr][sc]=newColor
            bfs(sr,sc,oldColor)
            return image

# Method 2 : DFS
class Solution:
    def floodFill(self, image: List[List[int]], sr: int, sc: int, newColor: int) -> List[List[int]]:
        rows = len(image)
        cols = len(image[0])
        directions = [(0,1),(1,0),(-1,0),(0,-1)]
        
        def dfs(row,col,oldColor):
            for dx,dy in directions:
                x = row+dx
                y = col+dy
                if x<rows and x>=0 and y<cols and y>=0 and image[x][y]==oldColor:
                    image[x][y]=newColor
                    dfs(x,y,oldColor)
        
        if image[sr][sc]==newColor:
            return image
        else:
            oldColor = image[sr][sc]
            image[sr][sc]=newColor
            dfs(sr,sc,oldColor)
            return image
           
```
