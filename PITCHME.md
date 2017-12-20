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

Scalaをとりあえず

- 書き始める
- 布教する
- チームで使う

うえで知っておくとよさそうなことを紹介します

---

## とりあえず書き始めるときに知っておきたい

- sbtは常駐させる |
- REPLと友だちになろう |
- ???でざっくりスケッチ |
- 謎の記号はscaps |


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
