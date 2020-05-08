# Solution
```
class Solution:
    def checkStraightLine(self, coordinates: List[List[int]]) -> bool:
        if not coordinates:
            return False
        
        if len(coordinates) == 2:
            return True
        
        (x1,y1) = coordinates[0]
        slope = None
        
        for x2,y2 in coordinates[1:]:
            if (x2-x1) == 0:
                return False
            if slope is None:
                slope = (y2-y1) / (x2-x1)
                continue
            
            if slope != (y2-y1) / (x2-x1):
                return False
        
        return True
           
```
