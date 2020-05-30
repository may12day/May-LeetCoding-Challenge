# Solution
```
import heapq
class Solution:
    def kClosest(self, points: List[List[int]], K: int) -> List[List[int]]:
        heap = []
        res = []
        for x,y in points:
            dis = (x**2)+(y**2)
            heapq.heappush(heap,(dis,(x,y)))
    
            
        for i in range(K):
            dis,point = heapq.heappop(heap)
            res.append(point)
        return res
        
```
