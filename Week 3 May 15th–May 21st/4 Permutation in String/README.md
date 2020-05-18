# Solution
```
class Solution:
    def checkInclusion(self, s1: str, s2: str) -> bool:
        DicS1 = collections.Counter(s1)
        DicS2 = {}
        for i in range(len(s2)):
            if s2[i] in DicS2:
                DicS2[s2[i]]+=1
            else:
                DicS2[s2[i]]=1
                
            if i>len(s1)-1:
                DicS2[s2[i-len(s1)]]-=1
                if DicS2[s2[i-len(s1)]]==0:
                    del DicS2[s2[i-len(s1)]]
            
            if DicS2 == DicS1:
                return True
        return False
```
