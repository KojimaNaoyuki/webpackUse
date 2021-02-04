# webpackUse
webpackを使ってweb制作するときの使用例

## 必要なインストールコマンド
- npm init -y
- npm install --save-dev webpack webpack-cli
- npm install --save-dev sass sass-loader css-loader style-loader
- npm install --save-dev postcss-loader autoprefixer
- npm install --save-dev file-loader
- npm install --save-dev babel-loader @babel/core @babel/preset-env
- npm install --save-dev core-js@3 regenerator-runtime
- npm install --save-dev eslint eslint-loader babel-eslint
- npm install --save-dev mini-css-extract-plugin
- npm install --save-dev html-webpack-plugin
- npm install --save-dev html-loader
- npm install --save-dev optimize-css-assets-webpack-plugin terser-webpack-plugin

## 必要ファイル
- .eslintrc
- babel.config.js
- package.json
- postcss.config.js
- webpack.config.js

## 初期設定状態
### entry
- ./src/index.js ← index(chunks)
- ./src/sub.js ← sub(chunks)

### output
- ./public/[name].[chunkhash].js

### ESlint
- "extends": "eslint:recommended"

## 機能
- 商用環境用にミニファイして出力
- 複数のhtmlファイルを個別にバンドルして出力
- 動的にバンドルしたjsファイルを読み込んだhtmlファイルを出力
- scssをcssに変換してcssは別ファイルにして出力(jsファイルにはバンドルされない)
- 自動でベンダープレフィックスが必要なものに付与する
- 画像をバンドルする
- babelでjsの最新構文をレガシー環境でも動作するようにトランスファイル
- ESlintによるjavascriptの構文チェック