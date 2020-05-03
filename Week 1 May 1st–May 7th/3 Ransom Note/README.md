# Solution
```
class Solution:
    def canConstruct(self, ransomNote: str, magazine: str) -> bool:
        myM=collections.Counter(magazine)
        myR=collections.Counter(ransomNote)
        
        for char,count in myR.items():
            if myM[char]<count:
                return False
        return True
```
