---
title: "JSTQBの行動規範について自分なりに考えてみる" # 記事のタイトル
emoji: "🌾" # アイキャッチとして使われる絵文字（1文字だけ）
type: "idea" # tech: 技術記事 / idea: アイデア記事
topics: ["test"]
published: true # 公開設定（falseにすると下書き）
---

# はじめに

JSTQBおよびISTQBには、「行動規範」というものがあります。
これらの行動規範は、テストエンジニアとしての普段の業務に対して常に意識すべきものであるものだと考えています。

というわけで、JSTQBの行動規範について考えてみました。

この文章を通じて、他のテストエンジニアの方々にとっても、より良いプロしての道を歩むための一助となることを心から願っています。
これをきっかけに、自分自身でも「テストエンジニアとしてどのような行動が正しいのだろうか」と考えるきっかけとなれば幸いです。

# 行動規範

ISTQBではソフトウェアテストに関与する人間として、8つの行動規範を示しています。
公人・顧客と雇用主・プロダクト・判断・マネジメント・専門職としての地位・同僚・自身です。
![](/images/ethics_all.png)

行動規範の前文には以下の内容が記載されています。

> ソフトウェアテストに関与することで、重要な機密情報を知る場合がある。特に、このような情報が不適切に使用されないようにするために行動規範が必要になる。
> ISTQBでは、ACM および IEEE が制定したエンジニアのための行動規範を基に以下の行動規範を示す。
> https://jstqb.jp/syllabus.html

「重要な機密情報」とありますが、これらは発売前の製品の情報をはじめとして、欠陥の情報やテストの情報など、品質に関する情報が挙げられます。
「不適切に使用」というのは、情報のリークに繋がったり、テストエンジニアという立場を悪用して利益誘導したりなどが挙げられると考えています。
これらは顧客をはじめとして、社会全体に対しても悪影響を及ぼします。
そのため我々テストエンジニアは行動規範を設定して、遵守すべきであるという考え方です。

本行動規範はACMとIEEEの行動規範が元になっているとのことですので、これらの記述もたびたび引用していきます。

## 公人
![](/images/ethics/公人.png)
> 公人 - 認定されたソフトウェアテスト担当者は、常に公人として行動しなければならない。
> https://jstqb.jp/syllabus.html

ここでは「公人」という訳語が当てられていますが、原文では「public interest」という単語を使っています。
公人と聞いてしまうと日本語のニュアンスだと公務員や政治家をイメージする人がいると思いますが、むしろ公益・公共の利益のために行動する個人と考えるといいかもしれません。

このpublic interestという言葉はこの行動規範にたびたび登場します。

ACMの行動規範では、PUBLICにおける個別の原則について、以下のように記載しています。
<!-- textlint-disable prh -->

> 1.03. Approve software only if they have a well-founded belief that it is safe, meets specifications, passes appropriate tests, and does not diminish quality of life, diminish privacy or harm the environment. The ultimate effect of the work should be to the public good.
> https://www.acm.org/code-of-ethics/software-engineering-code

<!-- textlint-enable prh -->

上記が示すようなpublic goodについては私自身も意識していきたいと考えています。

### 普段から意識していること

自分が関わっているソフトウェアが、社会にとって良いものかどうかを考えることにしています。
ただ単に特定のユーザーの利益になるのではなく、自分が関わった製品を通じて、より良い未来につながることを常に自信を持ちながら普段の業務に取り組みたいと考えています。

## 顧客と雇用主
![](/images/ethics/顧客と雇用主.png)
> 顧客と雇用主 - 認定されたソフトウェアテスト担当者は、常に公人として行動しつつ、顧客や雇用主に最大限の利益をもたらさなければならない。
> https://jstqb.jp/syllabus.html

「顧客や雇用主に最大限の利益を」というのは、ソフトウェアテストに限らず、社会人として求められるものだと考えています。
ここでいう公人とは「公人」の行動規範と同様に、公共の利益と私は解釈しています。

また、ACMの行動規範には以下のようにも記載しています。
> 2.09. Promote no interest adverse to their employer or client, unless a higher ethical concern is being compromised; in that case, inform the employer or another appropriate authority of the ethical concern.
> https://www.acm.org/code-of-ethics/software-engineering-code

上記の内容から、より高い倫理的懸念に対する責任は、顧客と雇用主よりも大きいことが見て取れるのではないかなと私は考えています。

### 普段から意識していること

顧客志向は品質保証の原則から言うまでもないことですが、自分を雇っている会社にとってもいい影響を与えることは意識しています。
単にいい製品を出すだけでなく、1人の社会人として適切に振る舞い、会社の文化自体を少しでもいい方向に繋がるような振る舞いをしたいと考えています。

## プロダクト
![](/images/ethics/プロダクト.png)
> プロダクト - 認定されたソフトウェアテスト担当者による成果物(自身がテストしたプロダクトやシステムに関するもの) は、プロフェッショナルとして高いレベルのものでなければならない。
> https://jstqb.jp/syllabus.html

ここでは「高いレベル」というこ言葉が使われていますが、原文では「the highest professional standards possible」とあります。
実際には「可能な限り最高の専門的水準」と訳すのが厳密かなと思います。

ACMの行動規範のPRODUCTには以下のような記述があります。
> Software engineers shall ensure that their products and related modifications meet the highest professional standards possible. In particular, software engineers shall, as appropriate:
> https://www.acm.org/code-of-ethics/software-engineering-code

ACMでは「products」となっている部分が、ISTQBでは「provide」となっている部分が興味深いと考えています。

### 普段から意識していること

普段からすべての成果物が最高ということはないですが、プロとして妥当な判断したうえで、恥ずかしくないレベルにすることは意識しています。
「テストなら誰でもできる」という言葉がありますが、私はそれに同意します。
同様に、プログラミングは誰でもできるし、営業も誰でもできると考えています。

ただ、それらの仕事や成果物がプロとして高い水準であることに違いがあると思っています。
その上で、私はプロとして恥ずかしくない成果物を常に作れるように意識しているのです。

## 判断
![](/images/ethics/判断.png)
> 判断 - 認定されたソフトウェアテスト担当者によるプロフェッショナルとしての判断は、誠実なものであり、かつ自身でなしたものでなければならない。
> https://jstqb.jp/syllabus.html

「誠実なもの」という言葉は、原文では「integrity」という単語が使われています。
integrityというと誠実という意味がありつつも、私が理解するニュアンスでは高潔さや完璧な状態を表すものではないかなと考えています。

また、「自身でなしたもの」には「independence」という単語が使われています。
この言葉には、プロとして他の人や組織から影響を受けないようなニュアンスがあるのではないかなと考えています。

ACMの行動規範には以下のような記述があります。

> 4.06. Refuse to participate, as members or advisors, in a private, governmental or professional body concerned with software related issues, in which they, their employers or their clients have undisclosed potential conflicts of interest.
> https://www.acm.org/code-of-ethics/software-engineering-code

こういった内容から、プロとしての自分の判断は自分自身の利益誘導に使うのではなく、高潔であり独立であることが求められると考えています。

### 普段から意識していること

テストをしている中で、自分自身が判断する立場になると、「テスターとしての自分が楽できる」「今は問題にならないけどリスクがあるな」という誘惑に駆られることがあります。
無理して犬の道を走るのはプロとしてふさわしくないことはもちろんですが、自分やチームの利益誘導のために自分の考えを表明しないことは「誠実ではない」と考えています。
あくまでいいプロダクトを通じていい顧客体験と社会を作るために、自分の判断が誠実で、独立していることは意識していきたいと考えています。

## マネジメント
![](/images/ethics/マネジメント.png)
> マネジメント - 認定されたソフトウェアテストマネージャおよびリーダは、ソフトウェアテストのマネジメントに対する倫理的なアプローチに同意した上で、これを推進しなければならない。
> https://jstqb.jp/syllabus.html

ここでは「ソフトウェアテスト担当者」ではなく、「テストマネージャーおよびリーダ」となっています。

「同意したうえで」という言葉がありますが、原文では「subscribe」です。
この言葉には、単に同意するだけでなく、より強く共感して、自分で考えて実装していくニュアンスがあると考えました。

### 普段から意識していること
私自身、マネジメントの立場に立つこともあります。
その際にはこの行動規範や自分自身の倫理観を設定したうえで、自分自身が体現できるように意識しています。
まだまだ未熟な部分はありますが、誰にも恥ずかしくないように行動したいと考えています。

## 専門職としての地位 
![](/images/ethics/専門職としての地位.png)
> 専門職としての地位 - 認定されたソフトウェアテスト担当者は、公共の利益に寄与することで、専門職としての地位向上に努めなければならない。
> https://jstqb.jp/syllabus.html

ここでも「公共の利益」という言葉が出ていて、いかに大切かといういことが読み取れました。

「専門職」というキーワードがありますが、原文では「Profession」であり、これは重要なキーワードだと言われています。
「Profession」という言葉には秋山さんの以下のnoteでも触れられています。
https://note.com/akiyama924/n/nbed4c70d39f4

「地位向上」という言葉がありますが、実は原文では「integrity」という言葉が置かれています。
これは単に他者からの評価、地位を向上するだけでなく、自分自身も高潔である必要があると私は考えました。

### 普段から意識していること

私自身はテスターですが、自分の働きが社会に貢献して、それが自分のテスターとして得られた知見や積み上げられた技術であることはチャンスがあれば言っています。
個人的にはいわゆる「テスターの地位向上」にはあまり興味がないです。
ただ、今まで積み上げられてきたテストの技術については、今後も正しく理解され、いい世界のために使われたいと思って行動しています。

## 同僚
![](/images/ethics/同僚.png)
> 同僚 - 認定されたソフトウェアテスト担当者は、同僚に対し公正かつ協力的でなければならず、ソフトウェア開発者と協調しなければならない。
> https://jstqb.jp/syllabus.html

一緒に仕事をする人には、フェアで協力的である必要がるという文です。

ここで面白いところは、ACMの行動規範に対して、以下の文章が追加されている部分だと思います。
「ソフトウェア開発者と協調しなければならない」

単なるテスト仲間だけを同僚と見做すのではなく、Software Developersとも協調が必要であることを釘刺されているように感じました。

### 普段から意識していること

同じチームであっても、自分の利益のために行動するのではなく公正で協力的であるということは特に意識しています。
最近ではプログラマーの人と働くこともあり、テストを通じて批判するだけでなく、一緒に作る仲間として一緒に作っていけるような行動を心がけたいと思っています。

## 自身
![](/images/ethics/自身.png)
> 自身 - 認定されたソフトウェアテスト担当者は、生涯その専門性を磨くための学習を続けるとともに、実践の場でも倫理的なアプローチを広めなければならない。
> https://jstqb.jp/syllabus.html

まさに、一生勉強という感じがしています。
また、「倫理的なアプローチを広めなければならない」ありますが、元の文言は以下の通りです。
> shall promote an ethical approach to the practice of the profession.
> https://www.istqb.org/what-we-do/

これらは広めるだけでなく、自分自身でも実践していく必要があるというメッセージが込められているのではないかと思っています。

### 普段から意識していること

この記事を公開しようと思ったのは、この行動規範を見返したからです。
私自身はまだまだ未熟ですが、この記事を通して少しでも行動規範について知ってもらい、私自身も体現していきたいと思っています。

# 参考文献
<!-- textlint-disable prh -->
- JSTQB.「JSTQB認定テスト技術者資格-シラバス（学習事項）・用語集-」. JSTQB認定テスト技術者資格.2024-11-12.https://jstqb.jp/syllabus.html .(参照2025-6-30)
- ISTQB.「What We Do - International Software Testing Qualifications Board」. International Software Testing Qualifications Board. 2025-6-30.https://www.istqb.org .(参照2025-6-30)
- the Association for Computing Machinery, Inc. and the Institute for Electrical and Electronics Engineers, Inc..「ACM Ethics」. The Official Site of the Association for Computing Machinery‘s Committee on Professional Ethics.. 2022-12-22.https://ethics.acm.org/code-of-ethics/software-engineering-code/ .(参照2025-6-30)
- Kouichi Akiyama.「62号：行動規範」. 62号：行動規範｜Kouichi Akiyama.2020-4-6.https://note.com/akiyama924/n/nbed4c70d39f4 .(参照2025-6-30)
<!-- textlint-enable prh -->

# おわりに：この文章に対する思い(意味のない自分語り)

私は以前からこの行動規範を重要だと考えていました。
これらの行動規範を自分ごととして読み取り、どのように理解し・行動するかという資料を作成したことがあります。

しかしながら、私の行動や言動が非倫理的であり、テストエンジニアとして行動規範や倫理について語ることにふさわしくないという思いを持っている人もいらっしゃると思います。
私の未熟さのため、さまざまな方にご迷惑をおかけしたこともあります。

「私にはテストエンジニアの倫理や行動規範について語るにふさわしくない」と思っています。
そのため、自分自身への自戒も含めて、これまで行動規範を言及するドキュメントは非公開としてきました。

しかし、この行動規範の重要性を改めて伝えたいという強い思いが残っていました。

私はこの思いを成仏させるため、批判を覚悟で「行動規範」について語ろうと思ったのでした。