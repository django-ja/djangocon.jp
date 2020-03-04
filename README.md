# DjangoCongress JP のサイト

このリポジトリーは https://djangocongress.jp/ の管理をしています。
基本的にHTMLをGitHubPagesでホストし、それをCDNを通して配信しています。
HTMLやCSSはビルドすることで `docs/` 以下に生成されます。
リポジトリー内にはソースになるファイルと `docs/` の両方を管理します。

## HTMLの書き方

`_templates/` ディレクトリー以下にHTMLファイルを配置してください。
Jinja2のテンプレートで画面を記述できます。

アンダースコア `_` で始まるHTMLはビルドされません。
Jinja2用の親HTMLや、include用の部分HTMLはこの名前にしてください。
また `_templates/components` には、全体で使うJinja2のマクロを管理しています。

ビルドされたHTMLは `docs/` 以下に配置されます。

## CSSの書き方

`_sass` 以下にSass、SCSSファイルを入れてください。
アンダースコア `_` で始まるファイルはビルドされません。

ビルドされたCSSファイルは `docs/static/css/` 以下に配置されます。

## 静的ファイルの置き方

`_static/` 以下に置かれた静的ファイル（画像、JS、CSS、フォント）は、ビルド時に `docs/static/` にコピーされます。

## ビルドの仕方

ビルドは手元のローカル環境で行い、ビルドされたファイルをリポジトリーに同梱してください。

[ruins](https://github.com/hirokiky/ruins/) というコマンド使ってビルドします。
コマンドは **リポジトリールートで実行してください** 。

```
$ pip install ruins
$ ruins
```
