# Maximum Depth of Binary Tree(104)
バイナリ ツリーのルートを指定すると、その最大の深さを返します。

バイナリ ツリーの最大の深さは、ルート ノードから最も遠いリーフ ノードまでの最長パスに沿ったノードの数です。

## Ex.
Input: root = [3,9,20,null,null,15,7]
Output: 3

Input: root = [1,null,2]
Output: 2

## 条件
> The number of nodes in the tree is in the range [0, 104].
> -100 <= Node.val <= 100

## 回答
``` python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        if root == None:
            return 0

        left_depth = self.maxDepth(root.left)
        right_depth = self.maxDepth(root.right)
        return 1 + max(left_depth, right_depth)
```

## 解法
再帰を使って解く問題  
左のリーフと右のリーフの最大に１を足した値を返す
