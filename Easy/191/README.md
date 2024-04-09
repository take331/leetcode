# Number of 1 Bits
整数nが与えられたときに、その数値のバイナリ表現に含まれる'1'の数を返す問題  

## Ex.
Input: n = 11
Output: 3

Input: n = 128
Output: 1

## 条件
1 <= n <= 2³¹ - 1

## 回答
``` python
class Solution:
    def hammingWeight(self, n: int) -> int:
        return str(bin(n)).count('1')
```

## 解法
組み込み関数`bin()`を用いた方法  
