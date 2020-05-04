# Solution
```
# Method 1

class Solution:
    def findComplement(self, num: int) -> int:
        res = ''
        for i in bin(num).replace("0b",""):
            if i=='0':
                res+='1'
            else:
                res+='0'
        
        return int(res,2)

# Method 2

class Solution:
    def findComplement(self, num: int) -> int:
        temp = num
        bit = 1
        while temp:
            num = num ^ bit
            bit = bit << 1
            temp = temp >> 1
            
        return num

```
