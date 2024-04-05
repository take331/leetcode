# Single Number(136)
整数値からなるリストが与えられる  
このリストに含まれている数値は同じ数が２つのものと、１つだけのものがある  
このリストから、自分と同じ数がないもの、単独の数値を見つける問題

## Ex.
Input: nums = [2,2,1]  
Output: 1

Input: nums = [4,1,2,1,2]  
Output: 4

## 条件
> 1 <= nums.length <= 3 * 10⁴
  
> -3 * 10⁴ <= nums[i] <= 3 * 10⁴

> 配列内の各要素は 2 回現れるが、1 つの要素は 1 回だけ現れる

## 回答
``` python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        op = nums[0]
        for i in range(1, len(nums)):
            op ^= nums[i]
            print(op)
        return op
```

## 解法
XOR演算子を用いた方法  
XORは異なる値の際には1に、同じ値の際には0を出力する  

| A | B | Q |
| - | - | - |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

また以下より、計算の順番によらず解は等しくなる
- a XOR b = b XOR a
- (a XOR b) XOR c = a XOR (b XOR c)

つまり、要素が2つある数値を隣り合うように並べ、残ったものを末尾に並べたリストとばらばらに並べたリストの解は同じになる  
- [6,6,8,8,2,2,1]
- [6,2,1,8,6,2,8]

よって、最終的な解は要素が１つだけのものになる
