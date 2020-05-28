# Solution
```
class Solution:
    def countBits(self, num: int) -> List[int]:
        dp = [0]
        for i in range(1, num + 1):
            dp.append(dp[i // 2] + i % 2)
        return dp
        
```
