# Two Sum
整数値から成るリストnumsとターゲットとなる整数値が与えられる  
和がターゲットとなるような2つの整数値のインデックスを求める問題  

## Ex.
Input: nums = [2,7,11,15], target = 9
Output: [0,1]

Input: nums = [3,2,4], target = 6
Output: [1,2]

## 解法
``` python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        map = {}

        for i, n in enumerate(nums):
            diff = target - n
            if diff in map:
                return [map[diff], i]
            map[n] = i
```
