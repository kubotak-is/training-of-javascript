# Installation

開発に際してマシンにnode.jsをインストールしましょう。<br>
node.jsは活発に開発が進んでいるため、通常のインストール方法ではなく、バージョン管理ができるものを選択すると良いです。<br>
今回はGithubスター数の多いnvm(Node Version Manager)を導入します。

---

## Windows

[nvm-windows](https://github.com/coreybutler/nvm-windows)

---

```
$ nvm
```
ヘルプが出ればインストール完了です。

---

最新版のnode.jsは以下のコマンドからインストールできます。
```
$ nvm install latest
```

特定のバージョンをインストールしたい場合は以下
```
$ nvm install [verison]
```
[リリースバージョン一覧](https://nodejs.org/ja/download/releases/)

---

インストールされたnode.jsのバージョンを確認する。
```
$ nvm list
```
「*」が先頭についているものが現在利用できるバージョンです。<br>

切り替える場合は以下
```
$ nvm use [version]
```

---

## Mac

[nvm](https://github.com/creationix/nvm)

---

```
$ git clone https://github.com/creationix/nvm.git ~/.nvm
$ source ~/.nvm/nvm.sh
```
あとはWindowsと同様

---

これでローカルマシンでJavascriptを開発する環境が構築できました。

---

## ファイルの作成
コマンドプロンプト及びターミナルから
```
$ vim test.js
```
でJavascriptファイルを作成しましょう。基本的にJavascriptの拡張子は`.js`が使われます。<br>
※Node.jsにおけるModuleとして利用する場合は`.mjs`やトランスパイル前提でES2015以降で書かれたファイルは`.es`、また、TypeScriptで記述されたファイルは`.ts`など、場合によっては上記の限りではありません。

以下コピー＆ペーストで構いません。作成した`test.js`に記述してみましょう。
```
var name = "Javascript";
console.log("Hello " + name + "!");
```

---

## コマンドでJavascriptの実行
先程作成したJavascriptファイルを実行してみましょう。

```
$ node test.js
```

`node [file]`と実行するとNode.jsがJavascriptファイルを実行します。
コンソールに以下の文言が出ていれば成功です。

```
Hello Javascript!
```

---

## ブラウザでJavascriptの実行

先程作成した`test.js`をブラウザで実行してみましょう。<br>
まずはHTMLファイルを作成します。
```
$ vim text.html
```

作成したHTMLに以下の記述をコピー＆ペーストしてください。
```
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
```
Hello Javascript!
```
が表示されているはずです。<br>

```
<script src="test.js"></script>
```
上記のHTMLタグによりJavascriptの読み込みと実行が行われます。<br>
`script`タグには`src`属性の他に、`type`や`charset`,`language`,`defer`, `async`などがありますがここでは説明を省略します。HTMLの学習と合わせて確認しましょう。<br>
また、以下の様に記述することも可能です。
```
<script>
var name = "Javascript";
console.log("Hello " + name + "!");
</script>
```
上記はインラインスクリプトと呼ばれる手法です。しかしながら、Content Security Policyの観点から有害とされている記述になるので利用は避けるべきです。

---

### [specification](?md=/docs/03-SPECIFICATION-01)
