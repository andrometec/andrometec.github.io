# ANDROMETEC 開発紹介サイト

有限会社アンドロメテックの開発紹介サイトです。

## 開発

開発中のページはローカルサーバーでプレビューできます。

### 準備

```shell
$ git clone git@github.com:andrometec/andrometec.github.io.git
$ cd andrometec.github.io
$ npm i #インストール
```

### コマンド

```shell
$ npm run watch #ファイルの変更を検知して stylus のコンパイル、ファイルのコピーなどを行います
$ npm run release #クリーンビルドします
$ npm run server #localhost:3000 で dist/ 以下を配信します
$ npm start # watch と server を実行します
```

`npm start` を実行し、ブラウザでプレビューしながら開発を進めるイメージです。

### ディレクトリ構造

|ディレクトリ|説明|
|:---|:---|
|`image/`|画像ファイル|
|`html/`|HTMLファイル|
|`stylus/`|Stylusファイル|
|`dist/`|公開用ファイル|

最終的に `dist/` 配下は以下のようになるため、画像ファイルやスタイルシートを参照するパスはこれに沿って設定する必要があります。

```shell
.
├── image
│   ├── and-logo-s.svg
│   └── and-logo.svg
├── index.css
├── index.css.map
├── index.html
├── team-airkep.css
├── team-airkep.css.map
└── team-airkep.html
```

## 更新

### `team-airkep.html`: リンクを準備中にする
`html/team-airkep.html` を編集します。
`li.main-nav-link` 要素の `class` に `disable` を追加すると `準備中` になります。


## 公開

dev ブランチにチェックアウトし `npm run deploy` を実行すると、プロジェクトルートに必要なファイルが全てコピーされ、master ブランチにコミットされます。
公開するには master を GitHub にフォースプッシュする必要があります。

```shell
$ git checkout dev
$ npm run deploy
$ git push -f origin master
```
