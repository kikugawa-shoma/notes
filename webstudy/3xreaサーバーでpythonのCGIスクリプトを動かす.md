# xrea サーバーでpythonのCGIスクリプトを動かす
## 必要だった作業
1. .htaccessの記述
2. test.pyの書き換え
3. パーミッションの設定

### 1 .htaccessの記述
.htaccess
```
Options +ExecCGI
AddHandler cgi-script .py

```
https://deepseo.co/htaccess/cgi-script-enable/

https://www.adminweb.jp/apache/cgi/index2.html

### 2 test.pyの書き換え
```
print("<head><meta charset="utf-8"></head>")
```
↓
```
print("Content-type: text/html;charset=utf-8\n\n")
```
修正前のコードはうろ覚え。htmlちゃんと勉強すればどこがおかしいのか分かりそう。

### 3 パーミッションの設定
xreaのサーバに`ssh xrea`で入り、`chmod 755 [filename]`でパーミッションを変更する。

## 覚えておいてもよいデバッグ方法
```
print("Content-type: text/html\n\nOK.\n")
exit(1)
```
上のコードを上から入れていく。バグがある場所が特定できる。http://www.tohoho-web.com/wwwcgi7.htm
