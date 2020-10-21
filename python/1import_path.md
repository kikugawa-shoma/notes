# 自作モジュール、パッケージのimport方法のまとめ
## モジュール、パッケージ、ライブラリの違い
簡単に言うと、モジュール＜パッケージ＜（ライブラリ）
***


- モジュール

.pyファイルのこと。ファイル名がモジュール名になる。普通はこのファイルに関数やクラスが定義されていてimportして使う。

- パッケージ

複数のモジュールをひとまとめにして整理して一つのディレクトリに入れたものがパッケージ。

ひとまとめにしたディレクトリに__init__.pyという名称のファイルを置くことで1つのパッケージとして扱われる。このときディレクトリ名がモジュール名となる。
```python
import matplotlib.pyplot as plt

plt.plot(x,y)
```
上のコードはmatplotlibというパッケージの中にあるpyplotモジュール（pyplot.py）に定義されているplot()という関数をimportして使っている。

- ライブラリ
pythonにおいては実は厳密な定義はない。他のプログラムから呼び出して使われることを前提とした汎用的なプログラム（集）のことをふんわりとライブラリと呼んでいるだけ

つまり関数、クラス、モジュール、パッケージはすべてライブラリと呼べなくもない

## import方法
自作のパッケージやモジュールをimportするときは同じ階層なら`.fuga`を使って相対インポート

しかし、親ディレクトリに使用したいモジュールやパッケージがあるときは相対パスでもエラー`ImportError: attempted relative import with no known parent package`が出てしまう。


※気を付けること：`from hoge import`の後に.が来てはいけない
```python
from matplotlib import pyplot.plot #NG
from matplotlib.pyplot import plot #OK
```

## 参考文献
モジュール、パッケージ、ライブラリの違い

https://snowtree-injune.com/2019/07/01/word-a0046-48-module-package-library/

自作モジュールのインポート方法

https://note.nkmk.me/python-relative-import/

from import asの使い分けの仕方

https://snowtree-injune.com/2018/10/11/import/

親ディレクトリからのimport

http://var.blog.jp/archives/81938617.html
