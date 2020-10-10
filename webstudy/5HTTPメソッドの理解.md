# HTTPメソッドの理解
とりあえずGETとPOSTさえ知っておけばよさそう。

## GETメソッド
URI(後述)で指定された情報を要求。ファイル名ならばそのファイルの中身を、プログラムならその出力を返す。

## POSTメソッド 
クライアントから名前と値のセットのデータをホストへ渡す。フォームデータを送るときなどに使用。
## GETとPOSTの違い
- GETはクライアントがサーバーのリソースを取得する際に使用される。

- POSTはクライアントがリソースに対してなんらかの処理を要求する際に使用される。

https://qiita.com/kanataxa/items/522efb74421255f0e0a1

http://www.cresc.co.jp/tech/java/Servlet_Tutorial/Att_02.htm
## URLとURIの違い
+ URI(Uniform Resource Identifier) : 名前や場所を識別するルールの総称

+ URL(Uniform Resource Locater)    : ページや画像などを取得したりするための場所とアクセス方法を指定するためのルール。

URIとURLは包含関係にある。(
<img src=
"https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Cmathrm%7BURI%7D+%5Cni+%5Cmathrm%7BURL%7D" 
alt="\mathrm{URI} \ni \mathrm{URL}">)

https://webtan.impress.co.jp/e/2010/03/09/7539

## URLの成り立ち
- スキーム

  httpやftpなど

- オーソリティ

  ドメインのこと（本当はドメイン以外にもユーザー名、パスワード、アクセスするポートなどが書かれることもある。）

- パス

  指定したオーソリティのなかでどのディレクトリ、どのファイルにアクセスするかを指定

- クエリ

  アクセス内容を細かく識別するもの。
  サーバ上のプログラムへの指示や命令が記入されている。

- フラグメント

  サーバーから送られた情報をクライアントが処理する際に使用
