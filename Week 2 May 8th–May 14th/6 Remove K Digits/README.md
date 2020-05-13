# Solution
```
class Solution:
    def removeKdigits(self, num: str, k: int) -> str:
        res = []
        n = len(num)

        if n == k: 
            return "0"

        for i in range(n):
            while k and res and res[-1] > num[i]:
                res.pop()
                k -= 1
            res.append(num[i])

# when number is in increasing order
        while k:
            res.pop()
            k -= 1
        
        final = "".join(res).lstrip('0')

        if len(final)!=0:
            return final
        else:
            return "0"
```
