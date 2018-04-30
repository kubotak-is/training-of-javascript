# Installation

開発に際してマシンにnode.jsをインストールしましょう。<br>
node.jsは活発に開発が進んでいるため、通常のインストール方法ではなく、バージョン管理ができるものを選択すると良いです。<br>
今回はGithubスター数も多いnvm(Node Version Manager)を導入します。

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