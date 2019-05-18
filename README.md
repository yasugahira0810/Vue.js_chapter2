---
theme : "Simple"
transition: "zoom"
highlightTheme: "darkula"
slideNumber: true
---

# 2章 Vue.jsの基本

---

## *はじめに*

### *注意事項*

- *このリポジトリは[[秋葉原] Vue.js入門 輪読会 2章 Vue.jsの基礎 (初心者歓迎！)](https://weeyble-js.connpass.com/event/131771/)の発表資料として用意したリポジトリです。*
- *書籍の要約は正体、担当者の理解で書いているところは斜体で記載しています。*
- *権利関係で問題があれば、対応するのでご指摘ください。*

--

### *2章サマリ*

---

## 2章 Vue.jsの基本

- 「文房具の購入フォーム」の作成を通して、Vue.jsの基本的な機能をマスターする。

---

## 2.1 Vue.jsでUIを構築する際の考え方

- jQueryとは違うのだよ、jQueryとは

--

### 2.1.1 旧来のUI構築の問題点

- jQueryェ。。。

--

### 2.1.2 Vue.jsのUI構築

- state

---

## 2.2 Vue.jsの導入

- [JSFiddle](https://jsfiddle.net/kitak/ufzsw5jL/)そのままだと動かない
- JSFiddleにそのまま描いても動かない。

--

Column Vue.jsの高度な環境構築

- ちゃんとやるならscriptタグに埋め込むのではなく、生成したファイルを読むこむべき

---

## 2.3 Vueオブジェクト

- グローバル変数Vue
  + コンストラクタ
  + モジュール

--

### 2.3.1 コンストラクタ
|オプション名|内容|紹介箇所|
|------|------|------|
|data|UIの状態・データ|2.5|
|el|Vueインスタンスを、マウントする要素|2.4|
|filters|データを文字列と整形する|2.7|
|methods|イベントが発生した時などの振る舞い|2.10|
|computed|データから派生して算出される値|2.8|
</span>

```js
var vm = new Vue({
    // ...
})
```

--

### Column MVVMパターン

- M: ビジネスロジックや内部の処理を担うModel
- V: レイアウトや見た目を担うView
- VM: View向けの状態の管理を担うViewModel

--

### 2.3.2 コンポーネント

---

## 2.4 Vueインスタンスのマウント

- マウント: 既存のDOM要素をVue.jsが生成するDOM要素で置き換えること
- 本節では2通りのDOM要素の指定方法を紹介
  + 2.4.1 インスタンス生成時にelプロパティで与える方法
  + 2.4.2 $mountメソッドを呼び出して後から指定する方法

--

### 2.4.1 Vueインスタンスの適用（el）

--

### 2.4.2 メソッドによるマウント（$mountメソッド）

- マウント対象のDOM要素がUI操作や通信などで遅延的に追加される場合に使う

--

### Column Vue.jsを既存アプリケーションに導入する

---

## 2.5 UIのデータ定義（data）

### dataプロパティ

- UIの状態となるデータのオブジェクトを指定
- Vue.jsのリアクティブシステムに乗る
- [dataプロパティのサンプル](https://jsfiddle.net/kitak/ufzsw5jL/4)

--

### 2.5.1 Vueインスタンスの確認

--

### 2.5.2 データの変更を検知する

```js
vm.$watch(function () {
  //鉛筆の個数
  return this.items[0].quantity
}, function (quantity) {
  //このコールバックは、鉛筆の購入個数が変更されたら呼ばれます
  console.log(quantity)
})
```

vm.items[0].quantity=2

---

## 2.6 テンプレート構文

### 2.6.1 テキストへの展開

--

### 2.6.2 属性値の展開


---