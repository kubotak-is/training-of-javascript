# Installation

開発に際してマシンにnode.jsをインストールしましょう。<br>
node.jsは活発に開発が進んでいるため、通常のインストール方法ではなく、バージョン管理ができるものを選択すると良いです。<br>
今回はGithubスター数の多いnvm(Node Version Manager)を導入します。

---

## Windows

[nvm-windows](https://github.com/coreybutler/nvm-windows)

---

```sh
$ nvm
```
ヘルプが出ればインストール完了です。

---

最新版のnode.jsは以下のコマンドからインストールできます。
```sh
$ nvm install latest
```

特定のバージョンをインストールしたい場合は以下
```sh
$ nvm install [verison]
```

インストール可能なバージョンは以下のコマンドで確認できます。
```sh
$ nvm list available
```
[リリースバージョン一覧](https://nodejs.org/ja/download/releases/)

---

インストールされたnode.jsのバージョンを確認する。
```sh
$ nvm list
```
「*」が先頭についているものが現在利用できるバージョンです。<br>

切り替える場合は以下
```sh
$ nvm use [version]
```

---

## Mac

[nvm](https://github.com/creationix/nvm)

---

```sh
$ git clone https://github.com/creationix/nvm.git ~/.nvm
$ source ~/.nvm/nvm.sh
```

Windowsと同様にnvmコマンドが使えることを確認
```sh
$ nvm
```

---

LTS版のnode.jsをインストールする
```sh
$ nvm install --lts
```

Mac/Linux版ではインストール後にuseコマンドを使わなくてもそのままインストールしたバージョンのnode.jsが反映されます。<br>
インストール可能なバージョンは以下のコマンドで確認できます。
```sh
$ nvm ls-remote
```

バージョン指定のダウンロードはWindows版同様
```sh
$ nvm install [version]
```

ダウンロードしたnode.jsの確認は
```sh
$ nvm ls
```

---

これでローカルマシンでJavascriptを開発する環境が構築できました。

---

## ファイルの作成
コマンドプロンプト及びターミナルから
```sh
$ vim test.js
```
でJavascriptファイルを作成しましょう。基本的にJavascriptの拡張子は`.js`が使われます。<br>
※Node.jsにおけるModuleとして利用する場合は`.mjs`やトランスパイル前提でES2015以降で書かれたファイルは`.es`、また、TypeScriptで記述されたファイルは`.ts`など、場合によっては上記の限りではありません。

以下コピー＆ペーストで構いません。作成した`test.js`に記述してみましょう。
```js
var name = "Javascript";
console.log("Hello " + name + "!");
```

---

## コマンドでJavascriptの実行
先程作成したJavascriptファイルを実行してみましょう。

```sh
$ node test.js
```

`node [file]`と実行するとNode.jsがJavascriptファイルを実行します。
コンソールに以下の文言が出ていれば成功です。

```sh
Hello Javascript!
```

---

## ブラウザでJavascriptの実行

先程作成した`test.js`をブラウザで実行してみましょう。<br>
まずはHTMLファイルを作成します。
```sh
$ vim text.html
```

作成したHTMLに以下の記述をコピー＆ペーストしてください。
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>TEST</title>
  <script src="test.js"></script>
</head>
<body>
</body>
</html>
```

---

作成したHTMLをブラウザで開きましょう。ここではChromeで開いていきます。<br>
開いたら`F12`もしくは`Command+Option+I`でDevToolsを起動し、Consoleのタブに切り替えましょう。<br>
Node.js上で実行したときと同じく

```sh
Hello Javascript!
```
が表示されているはずです。<br>

```html
<script src="test.js"></script>
```
上記のHTMLタグによりJavascriptの読み込みと実行が行われます。<br>
`script`タグには`src`属性の他に、`type`や`charset`,`language`,`defer`, `async`などがありますがここでは説明を省略します。HTMLの学習と合わせて確認しましょう。

---

また、以下の様に記述することも可能です。
```html
<script>
var name = "Javascript";
console.log("Hello " + name + "!");
</script>
```
上記はインラインスクリプトと呼ばれる手法です。しかしながら、Content Security Policyの観点から有害とされている記述になるので利用は避けるべきです。

---

### [specification](?md=/docs/03-SPECIFICATION-01)
