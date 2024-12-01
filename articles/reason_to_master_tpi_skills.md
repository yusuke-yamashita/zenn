---
title: "テストコンサルじゃなくてもテストプロセス改善技術を身につけ実践する意味と意義"
emoji: "🐒"
type: "idea" # tech: 技術記事 / idea: アイデア
topics: ["softwaretest","QA","test"]
published: true
published_at: 2024-12-06 00:00
---

# はじめに

本記事は「テストプロセス改善技術」を身につけ、実践する意味と意義について記載しようと思います。
テストプロセス改善技術の概要としては以下を参照してください。

https://www.aster.or.jp/business/testprocess_sg/pdf/ASTER_TPIGuide_v1.0.0.pdf

## この記事のコンテキスト

私は「TPI」という、江戸時代に作られたテストプロセス改善技術を取り扱う、古を受け継いだ専門家です。
私はTPIを強みのひとつとして取り扱っていました。
一方で。アジャイルQAとしてのカジュアル面接を進める中で、以下の感想をいただくことがありました。

- 「アジャイルではテストプロセス改善技術は必要ない」
- 「トップダウンのプロセスモデルは合わない」
- 「ウチは現場で起こった問題にきちんと向き合って対処しているから必要ない」

「現場によっては必要がない」はテストプロセス改善技術に限らず、すべての技術要素に当てはまるものです。
しかし、これらの意見を聞いて、私は素朴に「どうせプロとして試してもないし上辺くらいしか理解してないのによくそんなこと言えんな」と思ったことは否定できません。

本記事ではテストプロセス改善技術を少しでも学んだ人間として、テストプロセス改善技術がどのように有用で、どんな場合に使えないかを解説します。

## 本記事の意図

本記事は以下を意図しています。

- テストプロセス改善技術について、偏見を持っている人に誤解であると伝えたい
- テストプロセス改善技術について、その現場にとって適切な使い方をしなかったために嫌な思いを持ってる人に弁明したい
- 伸び悩んでるテストエンジニアの解決手段のひとつの手段として、テストプロセス改善技術があることを知ってほしい

すべての現場にテストプロセス改善技術を取り入れて欲しいという趣旨では決してありません。

# テストプロセス改善技術に対する誤解

## すべてがトップダウンアプローチである

テストプロセス改善技術の導入方法として、そのテストプロセス改善技術に習熟した人が主導して行うことが、今のところもっとも有用なアプローチだと考えます。
そのため、テストプロセス改善技術がトップダウンアプローチであるということは否定できません。

テストプロセス改善技術のアプローチは、大雑把に言えば以下の工程で実施されます。
1. 現状を知る
2. 現状を評価する
3. 改善策を計画する
4. 改善策を実行する
5. 以下ループ

こういった工程について、「突然コンサル的な人がやってきて、第三者的に現状をチェックして、改善策を押し付けてくる」といったような印象を持ってしまうことは仕方がないです。
しかし、それはテストプロセス改善コンサルが得意とするコンサル方法によって異なります。
上の工程の見方を変えると、OODAループにそっくりです。

そう考えるといかがでしょうか？あたかも自己組織化できそうな気がしませんか？（しない気もする）

実際の手法を例にとって考えてみます。
TPI NEXTという手法では、セルフアセスメントモデルとしての位置付けが強調され、有識者によるガイドの必要性を記述しながらも、チーム自身で自己認識して改善していくことが推奨されています。
テストプロセス改善技術の有識者が「コンサル的アプローチ」を選択しなければ、トップダウンなテストプロセス改善は回避できます。

そして、私は多くのアジャイル開発では「コンサル的アプローチ」ではなく、「コーチング的アプローチ」を行うことでテストプロセス改善技術を使った効率的なテストプロセス改善ができると考えています。

この論点については後ほど述べます。

## テストプロセス改善技術はガチガチのテストプロセス当てはめる

「テストプロセス改善技術」はものによっては「あるべき姿のテストプロセスモデル」が存在して、それに向かうための段階を表現されたものと思われています。
それは正しいです。

過去の蓄積された経験知から「いけてるテストプロセス」を定義して、そこに向かうのがテストプロセス改善技術です。
一方で、その現場のコンテキストや開発プロセスをきちんと理解せずに、「あるべき姿のテストプロセスモデル」にひたすら邁進するテストプロセス改善コンサルがいたとしたら、それはダメコンサルです。

本来、テストプロセス改善コンサルは、テストプロセス改善技術の段階モデルの達成方法を示すだけでなく、「あるべき姿のテストプロセスモデル」について、それらの存在意義をきちんと納得できるまで説明する必要があります。
あるいは、もう少し熟練したテストプロセス改善コンサルであれば、テストプロセスモデルの内容から、コンテキストにによって取捨選択するなどの柔軟な対応ができるべきです。

コンサルに対してもこれらかテストプロセスを改善していく人に考えて欲しいことがあります。
標準にただ盲目に従うのではなく、標準について本質的な理解を深め、そのプロセスを実施しないことによる問題やリスクをきちんと理解して、納得できるように説明できなければありません。

「僕はたくさん勉強しているから本質を理解してこう思います」だけでテストプロセスが改善できるほど、現場は甘くないのです。

## テストプロセスの問題はすべてふりかえりで解決する

「ふりかえりだけでテストプロセス改善はいいんです」という意見を持っている人はいます。
私はふりかえりが大好きですが、そういった意見にも私は別の意見を持っています。

第一に、テストの目的として「リスクを予防する」ということがひとつあります。
とくにプロダクトリスクについては「本番のバグを未然に防ぐ」という考えがあります。
そのため、「問題が起こってから対処する」ではなく、なるべく重要なリスクを排除するために、多面的な視点でいいテスト活動をする必要があります。
無知のまま問題が顕在化するのを待つのではなく、先に行動を起こして予防するのです。

第二に、ほとんどのふりかえり手法は特定のGoodプラクティスを提供することはなく、自チームの認識の範囲内での改善に留まるという点です。
チームの納得感としてはそれでいいと思います。
ただ、実践における失敗のみから学ぶ組織というのも健全ではないと考えます。
テストプロセスに限らず、すべてのプラクティスにおいて、「道しるべ」として何かしらの方向性があることが有用だと考えます。

## テストプロセス改善技術はそのまま適用すればいい

テストプロセス改善技術を適用することによって得られる改善策というものは、「経験的にこの優先度や順番でやったらいい感じになる」といったものです。
テストプロセス改善技術によって示される改善策は、思考停止でタスクとして積まれるのではなく、あくまでプロジェクトのいく末を判断するための「道しるべ」であるべきだと考えています。

たとえば、「バグ分析を行うこと」は有用なプラクティスと言われたりします。
しかしながら、それ以前に「テストの専門家がいること」や「テスト設計が適切に行われていること」などが満たされていないとあまり意味のある対策にはならないと、多くのテストプロセス改善技術では定義されています。

そうしたテストプロジェクトの全体像を把握して、テストプロセスの改善の1歩目として何をすべきかの「道しるべ」を提供するのがテストプロセス改善技術と考えています。

### おまけ：テストの専門家とテスト設計がバグ分析に優先する理由

「テストの専門家がいること」「テスト設計が適切に行われていること」が「バグ分析を行うこと」より優先する理由についても説明ができます。
テストの専門家によるテスト設計がきちんと行われていない場合、バグ分析のタスクについて、以下のような問題が起きることが考えられるからです。
- そもそもバグがきちんと出せていない
- バグ分析に必要な情報がテストからでは得られない
- バグ分析を実施しても開発やテストに適切に反映されない
- など

# テストエンジニアがテストプロセス改善技術を学ぶ意義

「テストプロセス改善技術に対する誤解」の章では、テストプロセス改善技術の誤解について記述しつつも、テストプロセス改善技術を取り入れるモチベーションについて記載しました。
取り入れるかどうかはこれらについて検討した上で、チームで決めたらいいと思います。

ここからはテストエンジニア自身がテストプロセス改善技術を学ぶ意義について記載します。
実はここからが本当に伝えたいことです。

## 徹底的な言語化ができる

テストプロセス改善技術の大まかな流れについては上記で記載しました。
すべてのフェーズで、テストプロセス改善エンジニアは徹底的な言語化が求められます。
すべての評価項目でそのテストプロセスがどういう状態かを文書化する技術、知識、知恵が求められます。
また、テストプロセス改善技術がアセスメントモデルの場合は聞き取るための説明能力、ヒアリング能力を含めたコミュニケーション能力が求められます。

これらは単純にJSTQBやTMapなどのプロセスモデルを学ぶだけでは得られない、「プロセスをインスタンス化する力」が得られます。
実務において、他のテストエンジニアと一緒に働くだけでなく、開発者やその他のロールに対して、テストプロセスを納得感を保ちながら進めるための大きな力になります。

## テストプロセスへの深い理解ができる

半端なテストプロセス改善技術者になるなら深い理解はできないですが、まじめにテストプロセス改善技術を適用しようと思ったらこう思うはずです。

「なんでこのプロセスはこうあるべきなんだ？」と。

テストプロセスを構成する何百というプラクティスはすべて導入する理由や目的があります。
テストプロセス改善技術をまじめに学ぶということは、それらを理解する機会を強制的に与えられるということです。

「ISTQBがベストプラクティスって言ってるからベストプラクティスなんだ」という思考停止した人がいるなら、それはダメコンサルです。

きちんと現状を言語化して、その現状に適したGoodなプラクティスを提示することができるのが、Goodなテストプロセスコンサルです。

「テストの技術を学んでもアジャイルでは通用しない」と言ってる人もいます。
私はその意見は間違っていると考えます。

2024年現在、シフトレフトやホリスティックテストなどのアジャイルテストの技法のほとんどは、既存のテストの技術の応用でできていると私は考えています。
そのため、たとえアジャイル開発にいたとしても、本質的な理解をするためにも既存のテストプロセスモデルのGoodプラクティスや技術を学ぶことは有用だと考えています。

## テストプロセス改善技術はコンサルじゃなくても使える

テストプロセス改善技術はコンサルじゃなくても使えます。

テストプロセス全体を客観的に判断して改善に向かうことができる技術として使って欲しいです。

自身もテスト実行を行い、テストの業務に忙殺されているアジャイルテストエンジニアは少なくないと思います。
そんな中で、目の前のテストケースの修正だけを改善としてもいいと思います。
しかし、一度テストエンジニアとして立ち止まってみて、「全体はどうなんだろう？」と考えることができるとよりよいと私は思います。

そういった考えになる手助けとして、テストプロセス改善技術を使って欲しいです。

# これからのテストプロセス改善技術

これからのテストプロセス改善技術についても考察してみます。
これは日本人である私が日本語で得られた情報のみを考えて発信するものですので、世界的には違うトレンドがあるかもしれません。

## 既存のテストプロセス改善技術にはアジャイル完全サポートではない

多くのテストプロセス改善技術やフレームワークはアジャイル開発を前提としていません。
そのため、元となったテストプロセスモデルがアジャイルに適していないと、不要なプラクティスを適用してしまう場合があります。

また、アジャイルフレームワークも一部存在しますが、それらには具体的に評価するための項目やプラクティスが用意されていません。私は見たことありません。
なので、セルフアセスメントの道具としては使えるとは思いますが、技術として再現性のあるものではないのではないかと思っています。

アジャイルにおいて、テストプロセス改善技術がそもそもいらないのか、それとも新しい何かが生まれるのか、はこれからもウォッチしていきたいと思っています。

それか、私が考えるべきなのか。。

## テストプロセスコンサルのありかたが変わる

アジャイル開発において、テストプロセスコンサルは「コンサル的アプローチ」から「コーチンング的アプローチ」に変更した方がうまく働けると思っています。

「コンサル的アプローチ」とは、第三者として評価、レポートの提出、改善策の提示といった働き方を想定しています。

「コーチング的アプローチ」では、少し違います。
テストエンジニアを含むエンジニアとの対話を重視して、問いをベースに評価の段階から納得感を醸成しながら進んでいきます。
アウトプットとして何かのレポートがなくても、チームと伴走して、自己管理で成長できる組織を作ることがゴールと想定しています。

しかし、これからテストプロセス改善技術を学ぶコーチング的なアプローチをする人がレポーティングをしなくていいかというと、そうでもない気がしています。
レポーティングは言語化の機会となるので、クライアント的に実施する機会がなくても、きちんと武器として携帯し、いつでもできる状態でいた方がいいと思います。

# おわりに

ここまで読んでもらって本当にありがとうございます。
私の心を傷つけない範囲で批判やコメントは大歓迎ですのでよろしくお願いします。