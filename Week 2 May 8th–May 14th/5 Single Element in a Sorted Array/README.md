# Solution
```
# Method 1
class Solution:
    def singleNonDuplicate(self, nums: List[int]) -> int:
        if len(nums) == 1:
            return nums[0]
        left,right = 0,len(nums)-1
        while left<=right:
            mid = (left+right)//2
            if nums[mid]!=nums[mid-1] and nums[mid]!=nums[mid+1]:
                return nums[mid]
            elif nums[right]!=nums[right-1]:
                return nums[right]
            elif nums[left]!=nums[left+1]:
                return nums[left]
            else:
                left+=2
                right-=2

#Method 2
# class Solution:
#     def singleNonDuplicate(self, nums: List[int]) -> int:
#         if len(nums) == 1:
#             return nums[0]
#         left, right = 0, len(nums)-1
#         while left < right:
#             mid = int((left + right)/2)
#             if (mid % 2 == 1 and nums[mid - 1] == nums[mid]) or (mid%2 == 0 and nums[mid] == nums[mid + 1]):
#                 left = mid + 1
#             else:
#                 right = mid
#         return nums[left]
           
```
