---
title: "テスト技法ってなんなの？"
emoji: "🦔"
topics: ["softwaretest","QA","test"]
published: true # 公開設定（falseにすると下書き）
published_at: 2024-12-05 00:00
---

# はじめに

この記事では「テスト技法」について解説します。
テスト技法について、本質的なところを理解せずに、「教科書に書いてあるからなんとなく使っている」という人をみることがあります。

この記事ではそんな人に向けて、テスト技法の存在意義について語ろうと思います。

と、思っていたら、株式会社ベリサーブの長谷川さんが私が言いたいことを端的に表した記事を記載されていました。

https://www.veriserve.co.jp/helloqualityworld/media/20240313001/

> 先に、テスト技法が何のためにあるのかについて説明します。ずばり、それはカバレッジのためです。
> テスト技法の本質 2024.03.13 記事：長谷川聡

ぶっちゃけ私が一番主張したいことは上のことそのままです。
ですので本記事ではもう少し私の色を出した思想強めの主張を記載します。

# テスト技法とは

テスト技法とはズバリ、カバレッジのためです。
そしてもうひとつ付け加えるならば、カバレッジは「テストケース」によってカバーされると考えます。

もう少し私の言葉で表現すると、
テスト技法とは「カバレッジを満たすテストケースを生成する技術」です。

実際にJSTQB ALTAのシラバスでもテスト技法の欄には必ず「カバレッジ」の章があります。

## 超重要な「カバレッジ」という概念

テスト設計の本質は私は「カバレッジ」だと考えています。
- なんらかの**テストモデル**に対して
- なんらかのカバレッジ基準を元に
- カバレッジできるテストケースを導出する
がテスト設計という活動だと考えています。

カバレッジができていればテストケースは1つでもカバレッジを満たしていると考えています。
また、あるカバレッジ基準を満たすテストケースはそれぞれ重要度は同じであると考えています。

テストケースの重要度は「テスト条件」単位で設定され、それをカバレッジしている限り、複数のテストケースはすべて同じ重要度を持つと考えています。
テストケースによって個別の重要度が識別される場合は、個別のテスト条件が識別できると考えています。

## テストモデル

テスト技法の本質はカバレッジであると述べました。
「何をカバレッジするんだ」というのも大事です。

カバレッジするものは「モデル」a.k.a. テストモデルです。
以後は「テストモデル」とします。

「テストモデル」はISTQBやISO/IEC/29119で用いられている概念です。
一字一句違えない本当の定義は上記で確認してください。

「テストモデル」とは、私の言葉で言えば、「テストの対象をテスト可能な側面に抽象化したもの」です。

「テストモデル」でなく、単に「モデル」ともいう場合があります。
こちらについてはおそらく、テスト用のモデルとソフトウェア設計にも使えるモデルの2種類を想定しているのかなと思っています。

私にとっての「テスト技法」とは後者のソフトウェア設計で使用したモデルをテストケースに落とすことを指しています。
一方、あとでも触れますが、「テストモデル」を作ること自体は重要な技術だと考えています。

### モデルの拡大解釈

また、「ホワイトボックステスト」における「モデル」の考え方についても補足しておきたいです。
これは私の理解ですが、「コード」を「行として認識する」、「分岐として認識する」など、それぞれ固有のモデル化が可能であると私は考えています。

プログラミング言語で表されている時点でモデルとも言えるかもしれません。
ですので、私にとって「ホワイトボックステスト」は「モデルをカバレッジしている」という定義に矛盾はありません。

また、モデルについては必ずしもUMLなどの図に表現されるものである必要だとは考えていません。
自然言語で表現されたものも「モデル」と考えています。
これは、「自然言語で表現された要求」などもテストカバレッジの対象に入ると考えるからです。

どんなテストモデルが適切かはテスト対象とテスト条件によって識別されると考えていますが、
これについては別の記事で記載しようと考えています。
あるいは他の方が記述した別の文献をあたってください。

### smalltalk「悲しきかなカバレッジアイテム」

当初の記事では「テストモデル」の代わりに「カバレッジアイテム」という言葉を使っていましたが、これの定義は今と昔では変わってしまっているようです。
たとえばJSTQBの場合

カバレッジアイテム（coverage item）version2
> テスト技法を使用して、一つ以上のテスト条件から導出される属性または属性の組み合わせ。テスト実行の完全性を測定するために使用する。
> https://glossary.istqb.org/ja_JP/term/coverage-item-2-1

カバレッジアイテム（coverage item）version1
> テストカバレッジの基礎となる実体や属性。たとえば、同値分割やステートメント。
https://glossary.istqb.org/ja_JP/term/coverage-item-1

version1では「同値分割」や「ステートメント」といった**テスト技法適用前**がテストモデルとなっています。
version2では「属性または属性の組み合わせ」ということなので、テストモデルに対して**テスト技法適用後**に導出されるものなっています。


ISO/IEC/IEEE29119でも扱いが変わっているようですが、2023年versionを保有していないため、言及するのみにとどめておきます。


## ピンポイントと網羅

テスト条件を識別するにあたり、「テスト観点」という言葉を使う人々がいます。
VSTePを使う人々などですね。

そうでない人も普通に使っています。
https://www.jaspic.org/event/2006/SpiJapan/proceedings/4c1.pdf

あるいはテスト設計コンテストの文脈では「ピンポイント型のテスト観点」「網羅型のテスト観点」という言葉があります。
https://www.aster.or.jp/business/contest/doc/2021_chibicon_V1.0.0.pdf

ピンポイントと網羅はそれぞれ補完関係にあります。

この記事では上記の定義や使われ方を尊重した上で、「テスト技法のキモはカバレッジによる網羅である」というスタンスを取りたいです。
ピンポイント型のテスト観点であろうと、網羅型のテスト観点であろうと、それらはテストケースによって「網羅されている」と定義付けします。

## ブラックボックステスト技法

ブラックボックステスト技法には色々あります。
私はオレオレ定義にて、ブラックボックステスト技法の種類を識別しています。

これは教科書的にコンセンサスを得られているものではなく、やましたの認識です。

### テストケースを作るためのテスト技法

- デシジョンテーブルテスト
- 状態遷移テスト
- ユースケーステスト

これらの特徴は「ソフトウェア設計で導出した設計書をテストケースでカバレッジするだけ」という性質を持っていることです。
テスト技法としては「デシジョンテーブル作成」「状態遷移表や図の作成」はスコープに含まれていないと思っています。
元々ソフトウェア設計技法として「デシジョンテーブル」「状態遷移」というものがあり、これらをカバレッジするテストケースを生成するのがテスト技法であるという認識です。

**ただこれは「デシジョンテーブル作成」「状態遷移表や図の作成」がテストエンジニアに不要と言っているわけではありません。**

ソフトウェア開発において、デシジョンテーブルや状態遷移図が必ずしも作成されるとは限りません。
それらを作成することはエンジニアとして重要なスキルだと思っています。

ただ、それは「ソフトウェアや仕様の性質がその設計技法に適している場合に有効である」ということを忘れてはいないと思います。
テストするからといってなんでもデシジョンテーブルで表現するテスターはテストエンジニアとして未熟だと言わざるを得ません。

また、テスト技法として「デシジョンテーブル作成」「状態遷移図の作成」は含まれていないという立場の人間ですが、エンジニアとして持っていて悪いことはないスキルだと思っています。
ですので、「デシジョンテーブル作成」ができるテスターは胸を張って「私はエンジニアです」と名乗っていいんじゃないかと思っています。

### テストをする/しないの理由付けのための技法
- 同値分割法
- 境界値分析
- ペアワイズとか直交表とかその辺

これらはおそらく、ソフトウェア設計で使う技法ではありません。多分。違ったら教えてください。
上記は「テストをする/しないの理由付け」のためにある技法だと思いました。

「同値パーティションに含まれる場合はテストしない」「ペアワイズは網羅する」などですね。
これらは上記の理由づけによってなされるテストケースを導出することが目的のテスト技法です。

### よくわからんテスト技法
- クラシフィケーションツリー
クラシフィケーションツリーはどこからやってきて、どこに行くのか私はよくわかっていません。
入力値とかの整理に使うけど、とくにカバレッジとか導出しないような気がするなあとか思っています。

クラシフィケーションツリーについてはあきやまさんの記事が詳しいです。

https://note.com/akiyama924/n/ncd1b91277726

このテスト技法自体は仕様の整理などによく使います。

## ホワイトボックステスト技法

ホワイトボックステスト技法はさまざまありますが、「特定のコードカバレッジを満たす」ということであると理解しています。
テストベースがコードになるので、「コードをこれだけカバレッジしました」以上の意味は持たないと考えています。

一方で「制御フローテスト」「データフローテスト」などはコードカバレッジではないかも？と思ったりします。
その点はブロッコリーさんから指摘をいただいています。
https://twitter.com/nihonbuson/status/1781937435125146102?s=61&amp;t=ao9ER3quoqKpLRig291r7w

ホワイトボックステストの定義については「動いているソフトウェアのコードやデータからカバレッジするものを決める」でいかがかと思いましたが、
これで正しいかどうかは有識者の意見を待ちたいと思っています。

また、ホワイトボックステスト技法は単体テストの文脈で語られます。
単体テストにおいて、ホワイトボックステストで不十分であることは「Effective Software Testing」という本が詳しいです。
私はこの本でメイクセンスしました。

https://www.effective-software-testing.com/

### プロパティベースドテストの位置付け

プロパティベースドテストは主に単体テストの技法ですが、私はブラックボックスかグレーボックスのテストではないかと考えています。

## 経験ベースのテスト技法

経験ベースのテスト技法も存在します。
「チェックリストベースドテスト」「エラー推測」などです。
これらもテストベースとして「何らかの経験」が存在して、それをカバレッジするテストケースを生成するという理解を私はしています。

「探索的テスト」だけは扱いに困ります。

探索的テストは本来的にテスト対象から学び、テストケースの作成と評価を同時に行うからです。
この場合のテストモデルは「テスターが認知したソフトウェアのふるまい」になるのでしょうか。
謎。

何にせよ「テストケースを導出することができる」という点で、「探索的テスト」を使うのならばテスト技法の仲間に入れてあげてもいいと思っています。
「テストチャーターを網羅してテスト設計しています」なら探索的テストをやらなくてもいいかなと思います。最初からテスト設計をしてほしいと考えます。

そうでなければ探索的テストは下記のテストエンジニアリングかな〜と思ったりします。

# オレオレ定義:テストエンジニアリング

テストケースを導かないさまざまテストの技術はテスト技法いわゆるTest Techniqueではなくて、なんと呼べばいいのでしょうか？

そこで私は「テストエンジニアリング」という言葉を提案したいと思います。

テスト技法だけでなく、さまざまな技術を用いてテストを行います。
効果的、効率化、納得感を高めたり、説明力を高めたり、いろんな有益なフィードバックする。
これらは全部「テストエンジニア」による「テストエンジニアリング」と呼称するのはいかがでしょうか。

# おわりに

テストエンジニアリングのくだりは共感してもらえたら嬉しいですが、業界に混乱を招きたくないので、別に積極的に使って欲しいとは思っていません。
なんとなく言ってみたかっただけです。