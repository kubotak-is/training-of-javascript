# Introduction

この資料ではJavascriptを始めるにあたり、基礎的な知識を学習するためのものです。<br>
なるべく最新を追えるように加筆・修正していきますがECMAScriptは毎年追加があるので追従できていない場合があります。<br>
領域としてはフロントエンド向けとし、サーバーサイドのNode.jsの説明はしません。

---

## フロントエンドとはなにか

Javascriptを学習する前に、まずフロントエンド領域とは何を指すのかを考えてみましょう。<br>
広義な意味では「ユーザーと直接データをやり取りする領域」と考えられていますのでスマートフォン用アプリケーションもフロントエンドと呼べます。<br>
ですが、本稿に置いてはWebブラウザにおけるフロントエンド領域と限定します。<br>
技術スタックとしてはHTML,CSS,Javascriptが主な範囲となります。

---

## Javascriptとはなにか
プロトタイプベースのオブジェクト指向言語です。<br>
後述するES2015よりクラス構文も追加されています。<br>
Javascriptという呼び方は狭義ではMozillaが策定・実装したスクリプト言語を指し、ECMAインターナショナルが標準化したものをECMAScriptと呼びます。<br>
各ブラウザベンダーはECMAScriptを実装しています。

---

## Javascriptの歴史

### 1995年
Javascriptはネットスケープ社のブレダン・アイクによって開発され、当初はLiveScriptと呼ばれていた。<br>
後にサン・マイクロシステムズ（現Oracle）が開発したJavaの人気にあやかる様にJavascriptという名称になった。

### 1996年
Internet Explorer3.0が登場するもNetscape社(現Mozilla)からJavascriptのライセンスを利用できなかったため、JScriptという大半が非互換の言語が実装された。

### 1997年
JavascriptとJScriptの互換性がない状態を解決するためにECMAインターナショナルという標準機関に依頼<br>
ECMA-262 初版ができる

---

## Javascriptの歴史

### 1998-1999年
ECMA-262 第2版、ECMA-262 第3版まで順調に標準化される。第4版策定時にAdobe, Mozilla他とMicrosoft, Yahooが反発し標準化が進まなくなる。

### 2000年
Macromedia(現Adobe) Flashの台頭

### 2005年
GoogleがAjaxを用いたGoogleMapを公開。<br>
prototype.jsの登場し2010年にはjQueryの登場する

---

## Javascriptの歴史

### 2008年
GoogleChromeが公開。Javascript実行エンジンにV8が搭載される

### 2009年
ECMA-262 第5版が発表
V8エンジンで実行されるNode.jsが発表される

### 2010年代
数多くのJavascriptフレームワークが登場。Backbone.js Angular.js React.js Vue.js...<br>
タスクランナーも登場 Grant, gulp...

### 2015年
ECMA-262 第6版 (Harmony)、所謂ES2015が発表される。

---

## Javascriptの実行環境

- ### Chrome
   - V8(C++)
- ### Firefox
   - SpiderMonkey(C/C++)
- ### Safari
   - Nitro
- ### Internet Explorer/Edge
   - Chakra Legacy, Chakra Edge(C++)

---

## DOM API

`document.~` や `window.~` <br>
DOM(Document Object Model)はXML, HTML, SVGドキュメントをプログラミング言語で利用するためにモデル化されたもの。文章を木構造で表現していて、ノードはさらにイベントハンドラを持っている。<br>
**DOMはECMAScriptの仕様の一部ではありません**<br>
つまり、DOM APIを含めた仕様をJavascriptと一般的に呼ばれ、そうでないものをECMAScript, Node.jsと呼ぶことが多い<br>
DOM APIはDOM Level1~4をW3C、以降のDOM Living StandardをWHATWGが策定している。

[DOM Standard](https://dom.spec.whatwg.org)

---

## パッケージ管理

2018年現在でもっとも利用されているJavascriptのパッケージ管理ツールは**npm**です。npmのラッパーでありFacebookが開発した**yarn**も使われることがあります。
yarnは先行して.lockファイルの仕組みを持っていたりダウンロード速度が早く、ライブラリをフラットにインストールする特徴があります。
2018/04現在であればどちらを使っても特に問題ない。

---

## Javascriptの周辺技術

- Babel
- TypeScript
- FlowType
- Gulp
- Webpack

---

## Babel

ES2015以前のJavascript実行環境でも動作させるために変換させるトランスパイラ

---

## TypeScript
Microsoftによって開発されたJavascriptのサブセット・トランスパイラ<br>
Javascriptに静的型付けが加えられたプログラミング言語<br>
TSと略されることが多い。

---

## FlowType
Facebookによって開発されたJavascriptに静的型付けのための記法を追加したツール<br>
対応エディタでのチェックとトランスパイル時の型チェックが可能になる。

---

## Gulp
Javascriptタスクランナーツール<br>

---

## Webpack

JavascriptのバンドルからCSS、画像などをJavascript同様に扱うことができる。
近年のデファクトスタンダードのビルドタスクツール

---

## その他の周辺技術
この資料では紹介しないJavascriptの周辺技術はまだまだ数多くある。
メリット・デメリットを確認して利用するようにしましょう。

---

### [installation](?md=/docs/02-INSTALLATION)