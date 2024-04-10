#  Isomorphic Strings(205)
与えられた文字列s,tが同型であるか判定する問題  
文字列sの順序を維持しながら、出現する文字をすべて別の文字に置き換えた際に、文字列tを取得できるとき、これを’同型’という
## Ex.
- Input: s = "egg", t = "add"
- Output: true

- Input: s = "foo", t = "bar"
- Output: false

## 回答
``` python
class Solution(object):
    def isIsomorphic(self, s, t):
        return len(set(zip(s,t))) == len(set(s)) == len(set(t))
```

## 解法
組み込み関数`zip()`を使った解き方  
zip()は複数のリストをまとめてタプル型として返す関数  
例えば、s='bbbaaaba' , t='bbbbaaaa' の場合、  
`set(zip(s,t)`は、((b,b), (a,b), (a,a), (b,a))となる  
sとtが同型の場合、s,t,zip(s,t)の長さは等しくなるため、これを利用して判定を行う。
