# Pascal'S triangle
整数 numRows を指定すると、パスカルの三角形の最初の numRows を返す問題


## 条件
> 1 <= numRows <= 30

## Ex.
- Input: numRows = 5
- Output: [[1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1]]

## 回答
``` python
  class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        ans = [[1]]
        next = [1,1]
        i = 1
        while i != numRows:
            ans.append(next)
            tmp = []
            for j in range(i+2):
                if j == 0 or j == i+1:
                    tmp.append(1)
                else:
                    tmp.append(next[j-1]+next[j])
            next = tmp
            i += 1
        return ans
```

## 解法
インデックスが０のときの値は１  
各行の先頭と末尾は常に１である  
それ以外の値は、前の行の同じ列と１つ前の列の合計になる

