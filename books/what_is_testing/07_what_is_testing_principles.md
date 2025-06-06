---
title: "テストの7原則ってなんなの？" # 記事のタイトル
---

# はじめに

本記事は「テストの7原則」について解説します。

テストはさまざまなコンテキストによって、その現場にあったプラクティスが存在します。
そのため、たとえばテスト技法から学ぶべき人や、テスト計画から学ぶべき人など、さまざまな人が存在します。

一方で、「テストの7原則」についてはどんな現場でも適用できる基本的な考えなのではないかと思いました。
テストの7原則はさまざまなブログで言及されており、それらを確認するのがいいと思います。

本記事ではもう少し具体的にどういった場合に適用できるかを語ることを目指したいと思っています。

## 1.テストは欠陥があることは示せるが、欠陥がないことは示せない

ソフトウェアテストは、故障を起こすことで、欠陥の存在を示すことはできます。
変な動作がして、それを調べたら欠陥だったという感じです。
一方でソフトウェアに欠陥がないことを証明はできないと言われています。
いわゆる「悪魔の証明」です。

すべてをテストしてすべてのテストがパスすれば問題ないわけですが、「すべて」のスコープを示せるものを私は見たことありません。
これは、2番目の原則である「全数テストは不可能」にもかかわります。

欠陥というのは言葉が難しいですが、単なるコーディングミスだけでなく、さまざまな形で故障として現れるものです。
顧客にとって都合の悪いもの、あるいはそれを引き起こすものだと考えるのが良いと思います。

欠陥がない状態を証明するのは難しいですが、「欠陥が顕在化しない」ことを示すことは実は可能です。
顧客が全く使わない製品や、顧客が一切触らない製品は、欠陥があっても顕在化しません。
これは極端な例です。

テストは、欠陥がないことを示すことはできません。
しかし、さまざまな制約のなかで情報を集め、リリースの判断材料を提供するという重要な役割があります。

欠陥がないことは示せないからといって、テストは無意味な活動と言ってしまうのは違います。
情報を集め、意思決定をサポートするための重要なプロセスと位置づけるべきです。

## 2.全数テストは不可能

ソフトウェアテストにおいて、すべてをテストすることは、ごく単純なソフトウェアを除いて非現実的です。
特に、入力インターフェースを持つものや、複数の変数を参照するようなものは、組み合わせ爆発が起こります。
すべてのパターンを実行は不可能です。

ソフトウェアはハードウェアと違って、さまざまなインターフェースを自由に使われうるという事情があります。
これはソフトウェアのテストをさらに複雑にしています。

さらに、単純な組み合わせや入力パターンだけでなく、実際の品質保証においては、さまざまな利用方法やユーザーニーズ、セキュリティや非機能要件などを考慮する必要があります。
そのため、テストは複雑になります。
一般的に、作るべきものよりもテストすべきものの方が多いと思ってもいいでしょう。

このような状況下でも、テストの技術は以下の方法を提供しています。
- テスト技法を用いてカバレッジ基準を定め、その範囲内でテストを行なう
- テストケースの優先度付けを行なう
- さまざまな分析を行なってテストを行なう

たとえばユーザーの行動パターンやリスクを分析し、それらを納得できる形で網羅すればいかがでしょうか。
欠陥はあるかもしれませんが、リリースはできるかもしれません。

全数テストが不可能だからといって、テストを諦めるのではなく、「テストは情報提供である」ということをしっかりと理解し、そのなかで何をすればリリースできるのかを判断することが重要なのです。

## 3.早期テストで時間とコストを節約

これは、品質保証の基本原則である「原点思考」にも通じる考え方です。

ここでいうテストとは、動的テスト、たとえば単体テストだけでなく、レビューなどの静的テストも含みます。
ソフトウェア開発ライフサイクルの早期にこれらの「テスト」を実施し、欠陥を修正することで、結果的にコストと時間を節約できます。

こういった考えは「アジャイルでは違う」と思ったり、「仕様書レビューを徹底的にする」ことと思う人がいます。
それは誤解だと考えています。

アジャイル開発では、顧客と協力して開発を進め、場合によっては早期にプロトタイプを作成し、顧客からのフィードバックを迅速に取り入れます。
このフィードバックには、顧客の要求に合わないという内容も含まれることがあり、それは結果的に欠陥の発見につながっているという考え方です。

顧客の要求に合わないという結果は、レビューによって防げる場合もありますが、アジャイル開発では、顧客との協力とプロトタイピングを重視します。
迅速なフィードバックを通じて欠陥を発見することが最も効率的だと考えている場合にこれは成り立ちます。

この原則は、さまざまな開発手法や前提条件によって、具体的な実施方法は異なるかもしれません。
しかし、その重要性は普遍的だと考えています。

## 4.欠陥の偏在

ソフトウェアの欠陥は、特定のコンポーネントに集中する傾向があるという考え方です。
これは、特定のエンジニアのスキル不足が原因と考える人もいるかもしれませんが、実際にはそうではないケースが多いと思います。
欠陥は、コンポーネントが頻繁に呼び出されたり、インターフェースの自由度が高かったり、入出力のパターンが多岐にわたる場合に発生しやすくなります。
その部分の重要度が高かったり、そもそもアーキテクチャの問題だったりするでしょう。

そして、重要なことは、バグが偏在している部分をどのように特定するかだと考えます。
システムコンポーネントを切り口に分析したり、さまざまな利用パターンを想定したり、品質特性に着目したりすることで、欠陥の偏在を確認できるかもしれません。
製品をさまざまな観点から分析し、欠陥が偏在している部分を特定することが、テスターの腕の見せ所ではないでしょうか。

## 5.テストの弱化

この原則は、私にとって最も理解が不十分で自信のない部分です。
同じテストを何度も繰り返すと、新たなバグを発見する効果が薄れていくというものです。
これは、開発者やチームが学習することでバグを検出しなくなるのか、あるいは単純に同じテストを繰り返すだけではバグが見つからなくなるのか、その理由が明確ではありません。

引用元であるボリス・バイザーの「ソフトウェアテスト技法」では、この現象を「殺虫剤のパラドックス」に例えています。
殺虫剤を使い続けると、耐性を持つ害虫が生き残り、より強力な殺虫剤が必要になります。
ソフトウェアも同じように、同じテストを繰り返すうちに、そのテストで見つかるバグは減少し、より高度なテストが必要になるという考え方のようです。

たとえばチェックリストベースのテストや経験ベースのテストなど、さまざまなテストの手法があります。
これらの手法はものによっては標準やチェックリストを参照します。
これらは常に更新し、見直していく必要があります。

古から標準テスト観点を受け継いで、それを使い続けている組織もあるかもしれません。
こういった場合にも、標準の更新が必要かもしれません。

こういった場合を考えると、「テストの弱化」という原則は示唆的だと考えます。

## 6.テストはコンテキスト次第

この原則は、私がもっとも好きな原則の１つです。
セム・ケイナーが原点ということなので、おそらくコンテキストドリブンの考えから来ているとは思いますが、そうでなくても「テストはコンテキスト次第」という考え方は、まっとうな考え方だと考えています。

唯一絶対というアプローチは存在せず、さまざまな場合でさまざまなアプローチはテストがあり得るという考え方です。
これは、テストだけでなく、開発手法にも言えるかもしれません。

例えば、原子力発電所のテストとゲームのテストは、同じ手法、あるいは同じような考えの品質保証ができるとは言えないのではないでしょうか。

さまざまなコンテキストによって、さまざまなテストは肯定されるし、否定されうるということを理解してテストを進めることが必要だと私は考えます。

## 7.欠陥ゼロの落とし穴

ソフトウェアテストをたくさん実施し、欠陥がゼロになったとしても、落とし穴のある可能性があります。
テストが正しく行なわれていない場合、欠陥を見逃している可能性があるからです。

例えば、ユーザーのニーズや競合との差別化といった重要な品質目標を見逃したままテストを進めてしまう場合が考えられます。
欠陥として報告されなくても、全く使われないあるいは全く売れない製品ができてしまうことがあります。
これが、「欠陥ゼロの落とし穴」と呼ばれる現象です。

シラバスでは、「検証に加えて妥当性確認も実施すべき」と述べていますが、私もその意見に賛成しています。
妥当性というのも大事ですが、根本的な意味で意味をいえば、欠陥がゼロだからといって満足するのではなく、「正しくテストできているか」を常に意識して判断することが大切です。

真の品質とは、バグがないことだけでなく、ユーザーのニーズを満たし、市場で受け入れられる製品であることです。
テストはそのための手段であり、目的を見失わないように注意が必要です。

