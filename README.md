# Leet_code_75

### 1. Running sum of 1d array
      I. Input: nums = [1,2,3,4]                                                        II.Input: nums = [1,1,1,1,1]
         Output: [1,3,6,10]                                                                Output: [1,2,3,4,5]
         Explanation: Running sum is obtained as follows: [1, 1+2, 1+2+3, 1+2+3+4].        Explanation: Running sum is obtained as follows: [1, 1+1, 1+1+1, 1+1+1+1, 1+1+1+1+1].                                                                         

### Code: 
         class Solution:
         def runningSum(self, nums: List[int]) -> List[int]:
             i = 1
             while i<len(nums):
                  nums[i]+=nums[i-1]
                  i+=1
             return nums       
      
### 2. Find pivot index
       I.Input: nums = [1,7,3,6,5,6]
         Output: 3
         Explanation: The pivot index is 3. Left sum = nums[0] + nums[1] + nums[2] = 1 + 7 + 3 = 11 ,Right sum = nums[4] + nums[5] = 5 + 6 = 11
            
       II.Input: nums = [1,2,3]
          Output: -1
          Explanation:There is no index that satisfies the conditions in the problem statement.    
          
### Code:          
         class Solution:
         def pivotIndex(self, nums: List[int]) -> int:
         # Time: O(n)
         # Space: O(1)
         left, right = 0, sum(nums)
         for index, num in enumerate(nums):
             right -= num
             if left == right:
                 return index
             left += num
         return -1
### 3. Isomorphic String
       I. Input: s = "egg", t = "add"
          Output: true
      II. Input: s = "foo", t = "bar"
          Output: false
### Code: 
         class Solution:
         def isIsomorphic(self, s: str, t: str) -> bool:
             return len(set(zip(s, t))) == len(set(s)) and len(set(zip(t, s))) == len(set(t))










