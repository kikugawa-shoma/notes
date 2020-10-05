# ローカルでのwebサーバの起動

## ディレクトリ構成
```
C:.
└─test
    index.html
    test.py
```

## ファイル
index.html
```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>テストページ</title>
    </head>
    <body>
        <h1>こんにちは</h1>

    </body>
</html>
```

test.pyは空のファイル


## コマンド
ホームページのルートのディレクトリに移動
```
C:\Users\UserName>cd programming\web\test
```

webサーバを起動
```
C:\Users\UserName\programming\web\test>python -m http.server --cgi
Serving HTTP on 0.0.0.0 port 8000 (http://0.0.0.0:8000/) ...
```
上のコマンドを実行したうえでブラウザでhttp://localhost:8000/ にアクセス

## 参考文献
https://dackdive.hateblo.jp/entry/2016/01/22/100000

