# Solution
```
class Solution:
    def isPerfectSquare(self, num: int) -> bool:
        if num < 2:
            return True
        L , R = 2 , num
        while L<=R:
            mid = (L+R)//2
            if mid**2 == num:
                return True
            elif mid**2 > num:
                R = mid-1
            else:
                L = mid+1
        return False
           
```
