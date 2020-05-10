# Solution
```
class Solution:
    def findJudge(self, N: int, trust: List[List[int]]) -> int:
        if N==1 and not trust:
            return 1
        dic={}
        for p,t in trust:
            dic[p]=-1
            if dic.get(t):
                dic[t]+=1
            else:
                dic[t]=1
        
        for k in dic.keys():
            if dic[k]==N-1:
                return k
        return -1
           
```
