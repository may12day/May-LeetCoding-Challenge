# Solution
```
# LCS different format
class Solution:
    def maxUncrossedLines(self, A: List[int], B: List[int]) -> int:
        if not A or not B:
            return 0
        N1,N2 = len(A),len(B)
        dp = [[0 for _ in range(N2+1)] for _ in range(N1+1)]
        
        for i in range(N1):
            for j in range(N2):
                if A[i]==B[j]:
                    dp[i+1][j+1] = dp[i][j]+1
                else:
                    dp[i+1][j+1] = max(dp[i+1][j], dp[i][j+1])
                    
        return dp[N1][N2]
        
```
