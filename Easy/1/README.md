# Two Sum
整数値から成るリストnumsとターゲットとなる整数値が与えられる  
和がターゲットとなるような2つの整数値のインデックスを求める問題  

## Ex.
Input: nums = [2,7,11,15], target = 9
Output: [0,1]

Input: nums = [3,2,4], target = 6
Output: [1,2]

## 条件
>  2 <= nums.length <= 104
 
> -109 <= nums[i] <= 109

> -109 <= target <= 109

> Only one valid answer exists.  

## 回答
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

## 解法
enumrate関数を用いて、numsの要素とインデックスを辞書型変数mapに格納  
ターゲットと現在の値の差となる値が、mapに存在すればその値(インデックス)を返す

## 別解
``` python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in range(len(nums)):
            if (target-nums[i]) in nums[i+1:]:
                return [i, nums[i+1:].index(target-nums[i])+(i+1)]
```
