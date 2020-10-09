# ローカルでflaskの最小アプリを動かす

公式のドキュメントの通りにやるだけ。

## ファイル
minimum.py
```
from flask import Flask

app = Flask(__name__)


@app.route("/")
def hello():
    hello = "Hello world"
    return hello

@app.route("/test")
def test():
    hello = "こちらはテストです"
    return hello


if __name__ == "__main__":
    app.run(debug=True)
```

## コマンド
環境変数を設定する必要がある。windowsはsetを使えばよい。
```
(webapp) C:\Users\myname\programming\web\flask1>set FLASK_APP=minimum.py

(webapp) C:\Users\myname\programming\web\flask1>python -m flask run
 * Serving Flask app "minimum.py"
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [10/Oct/2020 00:08:40] "GET / HTTP/1.1" 200 -
```

## 結果
http://localhost:5000/

![result](https://github.com/kikugawa-shoma/notes/blob/master/webstudy/images/flask_helloworld.jpg)

http://localhost:5000/test

![result2](https://github.com/kikugawa-shoma/notes/blob/master/webstudy/images/flask_test1.jpg)
