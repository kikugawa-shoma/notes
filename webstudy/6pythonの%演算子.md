# markupsafe.escapeについて
そもそもマークアップ（markup）とマークダウンとは？
- マークアップ

文書を構成する文章や文字列（および図や表）に対して、
その論理的構成を明示し、どんな文書要素であるかを
（その範囲を含めて）マーク（指定）したテキストファイルである

具体例を言うとHTML/CSSやLATEXのこと
- マークダウン

マークアップを簡略化して手軽に書けるようにしたもの
## pythonにおける%演算子の2つの用法
- あまりを求める
```py
a = 100
b = 7
print(a % b)

# > 2
```
- formatメソッドと同じ働き。
```py
print("User %s desu" % "abc")
print("User {} desu".format("abc"))

# > User abc desu
# > User abc desu
```
## 本題markupsafe.escapeについて
特殊文字をエスケープさせた文字列を生成。
pythonでhtmlを書く際に多く現れる特殊文字(「<」や「>」など)をいちいち手動でエスケープさせることなくそのまま書いて`escape()`の中に放り込めばよくなる。
```py
from markupsafe import escape

print("User %s desu" % escape("tanaka taro"))
print("User %s desu" % escape("<h1>"))
print("User %s desu" % escape("</html>"))
"""
User tanaka taro desu
User &lt;h1&gt; desu
User &lt;/html&gt; desu
"""
```
