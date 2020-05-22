# Solution
```
# Method 1 : Bucket Sort O(n)
from collections import Counter
class Solution:
    def frequencySort(self, s: str) -> str:
        freqMap = Counter(s)
        res = ""
        bucket = [None for i in range(len(s)+1)]
        
        for char,freq in freqMap.items():
            if bucket[freq] is None:
                bucket[freq] = []
            bucket[freq].append(char)
            
        for i in reversed(range(len(bucket))):
            if bucket[i] is not None:
                for char in bucket[i]:
                    res += char * i
                    
        return res


# Method 2 : Using heap O(nlogn)
# from collections import Counter
# import heapq
# class Solution:
#     def frequencySort(self, s: str) -> str:
#         freqMap = Counter(s)
#         heap = []
#         res = ""
#         for char,freq in freqMap.items():
#             heapq.heappush(heap,(-freq,char))
#         while heap:
#             freq,char = heapq.heappop(heap)
#             res += char*(-freq)
#         return res
        



# Method 3 : Using Counter.most_common()
# from collections import Counter
# class Solution:
#     def frequencySort(self, s: str) -> str:
#         freqMap = Counter(s)
#         res = ""
#         for char,freq in freqMap.most_common():
#             res += char*freq
#         return res

```
