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
#!/usr/bin/perl
$latex = 'platex -guess-input-enc -src-specials -interaction=nonstopmode -synctex=1';
$latex_silent = 'platex -interaction=batchmode';
$dvips = 'dvips';
$bibtex = 'pbibtex';
$makeindex = 'mendex -r -c -s jind.ist';
$dvi_previewer = 'start dviout'; # -pv option
$dvipdf = 'dvipdfmx %O -o %D %S';
if ($^O eq 'darwin') {
    $pdf_previewer = 'open -a Preview %S';
} elsif ($^O eq 'linux') {
    $pdf_previewer = 'evince';
}
$preview_continuous_mode = 1;
$pdf_mode = 3;
$pdf_update_method = 4;
```
ここまでで`latexmk hoge.tex`で日本語を含むファイルがコンパイルできるようになるはず。

## VScodeでの設定
1. Latex workshopをインストール
1. settings.jsonの設定


