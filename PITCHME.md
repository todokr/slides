# とりあえずScalaを使い始めるときに  
# 知っておきたい10のこと


2017.12.21  
[@todokr](https://twitter.com/todokr)


---


## 誰だ


---


## 田所 駿佑

![todokr](./t.jpg)

- 株式会社ビズリーチ Scalaエンジニア
- 求人検索エンジン Webクローラーや広告システムの開発
- 一部ではエモジニアと呼ばれています
- 文字コードとかEmacsが好きなネオ老害


---

![クローリングハック](./crawling-hack.jpg)

---

![ソフトウェアデザイン1月号](./sd.jpg)

---

## 今日のお題

Scalaを

- とりあえず書き始める
- 布教する
- チームで使う

うえで知っておくとよさそうなことを紹介します

---

## とりあえず書き始めるときに知っておきたい

- sbtは常駐させる |
- REPLと友だちになろう |
- ???でざっくりスケッチ |
- 謎の記号はscaps |

---

### sbtは常駐させる
- 「Scalaはコンパイルが遅い」→ 毎回sbt立ち上げてない？
- 常駐させたままコンパイルを繰り返すとJVMのwarmupで速度向上。落としたら負け。
- `$ sbt compile` ではなく、`$ sbt` → `compile` or `~compile`

--- 

### REPLと友だちになろう

- Read Eval Print Loop
- `$ scala`
  - Scalaの標準ライブラリのみのインタプリタを開始
- `$ sbt console`
  - コンパイル済のソースと依存ライブラリにクラスパスを通して、Scalaインタプリタを開始
- scastie（https://scastie.scala-lang.org/）
  - ブラウザから手軽に試せる

---

### ???でざっくりスケッチ

- `???` というメソッド
- まだ実装していない部分をマークしておくためにある
- コンパイルできるが呼ぶと例外
- 引数や返り値の型を先に考えて、後から中身を実装するときに役立つ

```scala
def someNiceMethod(x: Int): Option[String] = ???
def otherCoolMethod(x: Option[String]): String = ???

val result = otherCoolMethod(someNiceMethod(42))
```

---
 
### 謎の記号はscaps

- `???`を筆頭にググラビリティの低いメソッドなどがある
- ググると悲しい結果になる
- そういうときはscapsで検索すると正体が分かる

---

## とりあえず書き始めるときに知っておきたい

- sbtは常駐させる
- REPLと友だちになろう
- ???でざっくりスケッチ
- 謎の記号はscaps

---

## 布教するときに知っておきたい

- とりあえず読ませる本・記事 |
- 学習のための良い資料 |
- 最後の手段 |

---

### とりあえず読ませる記事

- 興味を持ちそうな人に「これ読んでみなよ」と渡せるものがあると楽
  - [Scala先駆者インタビュー](https://www.atware.co.jp/search?q=Scala%E5%85%88%E9%A7%86%E8%80%85%E3%82%A4%E3%83%B3%E3%82%BF%E3%83%93%E3%83%A5%E3%83%BC&f_collectionId=546d8fc4e4b06f0363347eaa)
 - [Scala使用歴5年のプログラマが、この言語とその環境に関する神話を解き明かす](http://postd.cc/5-years-of-scala-and-counting-debunking-some-myths-about-the-language-and-its-environment/)
 - [実践ScalaでDDD](https://speakerdeck.com/crossroad0201/scala-on-ddd)
 
---

### 学習のための良い資料
 
- 「Scalaスケーラブルプログラミング」
  - 通称コップ本。教科書。
- [「ドワンゴ Scala研修テキスト」](http://dwango.github.io/scala_text/)
  - 入門的内容から関数型のエッセンスまでバランス良く含まれている
 - gakuzzzzさんの資料
   - [Readable Scala](http://gakuzzzz.github.io/slides/readable_scala)
   - [Refactoring in Scala](http://gakuzzzz.github.io/slides/refactoring_in_scala)

---

### 最後の手段
 - 「Scala 年収」でググらせる

## チームに導入するときに知っておきたい
- 教育もセットで考える
 - アドテクスタジオでは「アドテクDOJO（道場）⁠」という取り組みを定期的に開催しています。アドテクDOJO（道場）とは，「⁠師匠」と「弟子」の関係設定を設け，育成文化の一貫としてペアプログラミングを行う社内の取り組みです。これを利用してチーム内のメンバーとペアを組み，集中的にScalaの考え方や書き方を伝えました。
 http://gihyo.jp/dev/serial/01/cyberagent/0063
- どのくらい関数型スタイルを取り入れるかをちゃんと合意する
  Javaのような書き方もできるし、関数型言語的な書き方も可能になっているなど、少しずつ関数型言語のパラダイムに移行するということも可能です。
- 既に導入しているチームに聞きに行く
