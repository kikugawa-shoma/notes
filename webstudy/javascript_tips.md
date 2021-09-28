# javascript についてまとめ

## 目的

- javascript に関して忘れやすそうなこと、調べないと出てこなかった情報をまとめておく

## モジュールの import export

- 自作モジュールの import の際にエラーが出る場合の対応方法
- 状況

ディレクトリ構造

```
.
├── MyModule.js
└── module_user.js
```

`MyModule.js`

```javascript
function helloWorld() {
  console.log("Hello World!");
}

let tmp = "Yeah!";

export { tmp, helloWorld };
```

`module_user.js`

```javascript
import { tmp, helloWorld } from "./MyModules.mjs";

console.log(tmp);
helloWorld();
```

このまま`node module_user.js`で実行すると、

```
SyntaxError: Cannot use import statement outside a module
```

が出る。

対応方法は 3 つある（らしいが、3 しか再現しなかった）

1. 実行時オプションに`--experimental-modules`
1. `import`している側のファイルの拡張子を`js`から`mjs`に変更する
1. 同階層ディレクトリに`package.json`ファイルを適切に記入して作成

### 2.`import`する側・される側両方のファイルの拡張子を`js`から`mjs`に変更する

- `import`する側のファイルパスの拡張子も`mjs`に変更しておく

```
.
├── MyModules.mjs
└── module_user.mjs
```

実行コマンド

```
$ node module_user.mjs
```

### 3.同階層ディレクトリに`package.json`ファイルを適切に記入して作成

```
.
├── MyModules.js
├── module_user.js
└── package.json
```

`package.json`

```javascript
{
    "type":"module"
}
```

## CORS エラーの解決方法

- https://qiita.com/terufumi1122/items/39b2a3659bc585c07f64

- 解決方法例：ローカルホストでサーバーを立ち上げてローカルホストでアクセス

コマンド

```
npm install http-server
http-server
```
