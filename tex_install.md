# windowsでのtex環境の構築(texのインストールとVScodeとの連携)
やること
1. texliveのインストール
1.　.latexmkrcの設定
1. VScodeのsettings.jsonの設定


## texliveのインストール
1. https://texwiki.texjp.org/?Microsoft%20Windows に従ってisoイメージ(texlive2020.iso)をダウンロード(数GBあるので時間かかる)
1. isoイメージをマウント
1. 中のinstall-tl-windows.batを実行

`latexmk`コマンドが使えるようになっていれば成功

## .latexmkrcの設定

```Perl
$latex = 'platex -synctex=1 %O %S';
$bibtex = 'pbibtex %O %B';
$dvipdf = 'dvipdfmx %O -o %D %S';
$makeindex = 'mendex %O -o %D %S';
$max_repeat = 10;
$pdf_mode = '3';
```
ここまでで`latexmk hoge.tex`で日本語を含むファイルがコンパイルできるようになるはず。

参考 : http://wq1.github.io/blog/2015-06-21/

## VScodeでの設定
1. Latex workshopをインストール
1. settings.jsonの設定
```
{
    // 生成ファイルを削除するときに対象とするファイル
    // デフォルト値に "*.synctex.gz" を追加
    "latex-workshop.latex.clean.fileTypes": [
        "*.aux",
        "*.bbl",
        "*.blg",
        "*.idx",
        "*.ind",
        "*.lof",
        "*.lot",
        "*.out",
        "*.toc",
        "*.acn",
        "*.acr",
        "*.alg",
        "*.glg",
        "*.glo",
        "*.gls",
        "*.ist",
        "*.fls",
        "*.log",
        "*.fdb_latexmk",
        "*.snm",
        "*.nav",
        "*.dvi",
        "*.synctex.gz"
    ],
        // ビルドのレシピ
    "latex-workshop.latex.recipes": [
        {
            "name": "latexmk",
            "tools": [
                "latexmk"
            ]
        },
    ],

    // ビルドのレシピに使われるパーツ
    "latex-workshop.latex.tools": [
        {
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-silent",
            ],
        },
    ],
}
```


