# unittest の使い方

## ディレクトリ構成

`tests`ディレクトリ配下にテストコードのファイルを置いていくのが慣例

## テスト実行コマンド

```shell
python -m unittest discover tests/ module.to.path
```

## 慣例的な書き方

ファイル名は`test_my_module.py`

```python
import unittest
from my_module import my_func

class TestMyFunc(unittest.Testcase):
    def test_answer(self):
        self.assertEqual(expected,actual)

if __name__=="__main__":
    unittest.main()
```

ポイントは、

1. クラス名は Test から始めてキャメルケース

1. 1 つの関数ににつき 1 つのクラスを作る。

1. クラスのメソッドで作成した関数の各機能をテスト

1. `unittest.Testcase`を継承

[ドキュメント](https://docs.python.org/ja/3/library/unittest.html#unittest.TestCase.assertIsInstance)
にいろいろに詳しい使い方やいろいろな`assertXXXX`が載ってるよ。

`asertRaises`を使うと例外を raise することもテストできる。
使い方は少し特殊なので注意
