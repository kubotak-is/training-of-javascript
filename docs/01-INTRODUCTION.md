# Introduction

この資料ではJavaScriptを始めるにあたり、基礎的な知識を学習するためのものです。<br>
なるべく最新を追えるように加筆・修正していきますがECMAScriptは毎年追加があるので追従できていない場合があります。<br>
領域としてはフロントエンド向けとし、サーバーサイドのNode.jsの説明はしません。

---

## フロントエンドとはなにか

JavaScriptを学習する前に、まずフロントエンド領域とは何を指すのかを考えてみましょう。<br>
広義な意味では「ユーザーと直接データをやり取りする領域」と考えられていますのでスマートフォン用アプリケーションもフロントエンドと呼べます。<br>
ですが、本稿に置いてはWebブラウザにおけるフロントエンド領域と限定します。<br>
技術スタックとしてはHTML,CSS,JavaScriptが主な範囲となります。

---

## JavaScriptとはなにか
プロトタイプベースのオブジェクト指向言語です。<br>
後述するES2015よりクラス構文も追加されています。<br>
JavaScriptという呼び方は狭義ではMozillaが策定・実装したスクリプト言語を指し、ECMAインターナショナルが標準化したものをECMAScriptと呼びます。<br>
各ブラウザベンダーはECMAScriptを実装しています。

---

## JavaScriptの歴史

### 1995年
JavaScriptはネットスケープ社のブレダン・アイクによって開発され、当初はLiveScriptと呼ばれていた。<br>
後にサン・マイクロシステムズ（現Oracle）が開発したJavaの人気にあやかる様にJavaScriptという名称になった。

### 1996年
Internet Explorer3.0が登場するもNetscape社(現Mozilla)からJavaScriptのライセンスを利用できなかったため、JScriptという大半が非互換の言語が実装された。

### 1997年
JavaScriptとJScriptの互換性がない状態を解決するためにECMAインターナショナルという標準機関に依頼<br>
ECMA-262 初版ができる

---

### 1998-1999年
ECMA-262 第2版、ECMA-262 第3版まで順調に標準化される。第4版策定時にAdobe, Mozilla他とMicrosoft, Yahooが反発し標準化が進まなくなる。

### 2000年
Macromedia(現Adobe) Flashの台頭

### 2005年
GoogleがAjaxを用いたGoogleMapを公開。<br>
prototype.jsの登場し2010年にはjQueryの登場する

---

### 2008年
GoogleChromeが公開。JavaScript実行エンジンにV8が搭載される

### 2009年
ECMA-262 第5版が発表
V8エンジンで実行されるNode.jsが発表される

### 2010年代
数多くのJavaScriptフレームワークが登場。Backbone.js Angular.js React.js Vue.js...<br>
タスクランナーも登場 Grant, gulp...

### 2015年
ECMA-262 第6版 (Harmony)、所謂ES2015が発表される。

---

## JavaScriptの実行環境(ブラウザ)

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
つまり、DOM APIを含めた仕様をJavaScriptと一般的に呼ばれ、そうでないものをECMAScript, Node.jsと呼ぶことが多い<br>
DOM APIはDOM Level1~4をW3C、以降のDOM Living StandardをWHATWGが策定している。

[DOM Standard](https://dom.spec.whatwg.org)

---

## パッケージ管理

2018年現在でもっとも利用されているJavaScriptのパッケージ管理ツールは**npm**です。npmのラッパーでありFacebookが開発した**yarn**も使われることがあります。
yarnは先行して.lockファイルの仕組みを持っていたりダウンロード速度が早く、ライブラリをフラットにインストールする特徴があります。
2018/04現在であればどちらを使っても特に問題ない。

---

## JavaScriptの周辺技術

- Babel
- TypeScript
- FlowType
- Gulp
- Webpack

---

## Babel

ES2015以前のJavaScript実行環境でも動作させるために変換させるトランスパイラ

---

## TypeScript
Microsoftによって開発されたJavaScriptのサブセット・トランスパイラ<br>
JavaScriptに静的型付けが加えられたプログラミング言語<br>
TSと略されることが多い。

---

## FlowType
Facebookによって開発されたJavaScriptに静的型付けのための記法を追加したツール<br>
対応エディタでのチェックとトランスパイル時の型チェックが可能になる。

---

## Gulp
JavaScriptタスクランナーツール<br>

---

## Webpack

JavaScriptのバンドルからCSS、画像などをJavaScript同様に扱うことができる。
近年のデファクトスタンダードのビルドタスクツール

---

## その他の周辺技術
この資料では紹介しないJavaScriptの周辺技術はまだまだ数多くある。
メリット・デメリットを確認して利用するようにしましょう。

---

### [installation](?md=/docs/02-INSTALLATION)