# SPECIFICATION

## 変数/定数
ここでは変数と定数について説明していきます。<br>
変数とはザックリいうと「データの入れ物」です。プログラム処理の中で一時的に保持しておきたいデータを変数という名前に紐づけて保持します。

---

## 変数の宣言

変数を利用する場合は予め宣言が必要です。宣言とは変数の名前をJavascriptに登録し、値を格納するための領域をメモリに確保することを言います。
変数の宣言は以下のように`var`命令が利用できます。

```js
var 変数名 [= 初期値];
```

---

例：nameという名前の変数を宣言
```js
var name;
```

例：宣言したい名前が複数ある場合
```js
var firstName;
var secondName;
```

カンマを使うことで省略して宣言することも可能
```js
var firstName, secondName;
```

例：初期値を指定して宣言
```js
var name = 'Node.js';
var version = 10;
```

初期値を指定しない変数のみの宣言の場合、デフォルトで未定義（undefiened）という値が格納されます。

---

### Q. 宣言にvarは必要か

実際には宣言に`var`がなくてもJavascriptでは自動的にそれが変数であると解釈されます。<br>
しかしながら、以下のようなコードがあった場合

```js
name = 'satoshi';
function getPokemon () {
  name = 'pikachu';
  return name;
};
console.log(getPokemon());
console.log(name);
```
結果は以下になります。
```
pikachu
pikachu
```
これは意図した挙動でしょうか？<br>
`var`を宣言しない場合、その変数はすべてグローバル変数となるため、スコープ毎に利用することができなくなります。<br>
このようなコードは想定していない挙動になりやすく、また可読性も悪くなるので変数の宣言は`var`を利用しましょう。

---

### Q. 変数の名前はどうあるべきか
前提としてJavascriptでは以下のようなルールが存在します。

|規則|良い例|悪い例|
|:----|:----|:----|
|1文字目は英数、アンダースコア、ドル記号のいずれか|_name, $name|1name|
|2文字目以降は上記に加え数字のいずれか|name1|name-1|
|大文字、小文字は区別される|firstname, firstName|-|
|予約語(※1)||if, for|

※1.strictモードの有無で可変します。また、将来的に予約語に採用される可能性のあるものは避けましょう（enum, classなど）[MDN 予約語](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Reserved_Words)

---

#### 読みやすいコードにするために
リーダブルコードという本があります。<br>
また、Javascriptの記述に一定のルールを設けるスタイルガイドが存在します。<br>
参考にしましょう。

[Google Javascript Style Guide](https://google.github.io/styleguide/javascriptguide.xml)<br>
[Airbnb Javascript Style Guide](https://github.com/airbnb/javascript)

---

## ES2015からの変数の宣言

ここまで`var`を説明してきましたがES2015以降では利用されません。<br>
代わりとなる`let`, `const`の登場により、より厳格なルールの下プログラミングが行えるようになったためです。

### let
それでは`let`を見ていきましょう。<br>
```js
let name;
let firstName, secondName;
let msg = 'Message';
```
`var`と同じです。しかし次の点で`var`と異なります。

---

**変数の宣言の重複を許可しない**
```js
let name = 'satoshi';
let name = 'takeshi';
```
このコードは`SyntaxError: Identifier 'name' has already been declared`というエラーが発生します。<br>
`var`であればエラーにはなりません。これは`let`が変数の宣言の重複を禁止しているためです。

---

**ブロックスコープを認識する**

コードで説明すると以下のような相違があります。
```js
(function () {
  var index = 1;
  {
    var index = 2;
  }
  console.log(index);
}());
// 2
```

```js
(function () {
  let index = 1;
  {
    let index = 2;
  }
  console.log(index);
}());
// 1
```

---

### const

変数とは、「データの入れ物」と先述している通り、あとから中身を入れ替えることが可能なものを指します。<br>
一方、一度設定した値を変更できないものは定数と呼ばれます。<br>
ES2015以前では変数・定数のどちらも`var`で表現していましたが、ES2015以降は言語レベルでこの違いを表現できるようになりました。この定数は`const`で宣言します。<br>
※一部ブラウザでは独自仕様としてES2015以前から`const`が実装されていたが、言語仕様として登場したのがES2015以降

宣言は以下のように行います。
```
const 定数名 = 値;
```

また、先述していたスタイルガイドに習って定数も命名すると良いです。<br>
例: `const KEY_NAME = 'value';`

---

### Q. 定数の使い所

ある一つの処理のみならず、ある程度使い回す値であること、さらにその値は不変である場合は定数の出番です。<br>
そして、その定数はもしかしたら変更があるかもしれないし、変更される場合は一括で変わるという場合も効果的です。<br>
例えば消費税などは1.08という数字自体には数字という意味しか持ちません。

```
const CONSUMPTION_TAX = 1.08;
```

しかし定数化することで名前が付けられるのでその数字が消費税であることが読み取れることができるようになります。

---

### [データ型](?md=/docs/03-SPECIFICATION-02)

