# Solution
```
# Method 1

from collections import deque
class Solution:
    def firstUniqChar(self, s: str) -> int:
        d = {}
        q = deque()
        for i, x in enumerate(s):
            d[x] = d.get(x, 0) + 1
            if d[x] == 1:
                q.append((x, i))
            while q and d[q[0][0]] > 1:
                q.popleft()
        return -1 if not q else q[0][1]

# Method 2

class Solution:
    def firstUniqChar(self, s: str) -> int:
        d = {}
        for c in s:
            if c in d.keys():
                d[c] += 1
            else:
                d[c] = 1

        for i in range(len(s)):
            c = s[i]
            if d[c]==1:
                return i

        return -1 
```
