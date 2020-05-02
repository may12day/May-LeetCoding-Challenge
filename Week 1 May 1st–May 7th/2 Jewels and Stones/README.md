# Solution
```
class Solution:
    def numJewelsInStones(self, J: str, S: str) -> int:
        Jset = set(J)
        count=0
        for i in S:
            if i in Jset:
                count+=1
        return count
           
```
